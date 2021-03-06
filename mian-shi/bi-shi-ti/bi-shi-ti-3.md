# 笔试题3

## PHP

1. 写一段代码保证多个进程同时写入成功

```php
#加锁
function write($filepath,$data) {
     $fp = fopen( $filepath, 'a' );   //以追加的方式打开文件，返回的是指针
 do{
 　　 usleep( 100 ); 　　　　　　//暂停执行程序，参数是以微秒为单位的
 }while( !flock( $fp, LOCK_EX ) );　　//以独享写入的方式锁定文件，成功则返回TRUE，否则FALSE
}
 $res = fwrite( $fp, $data."/n" );　　// 以追加的方式写入数据到打开的文件
 flock( $fp, LOCK_UN );　　　　　　//解锁，以让别的进程进行锁定
 fcloce( $fp );　　　　　　　　　　　//关闭打开的文件指针
 return $res;　　　　　　　　　　　　//返回写入结果
}
```

[https://www.cnblogs.com/gengyi/p/6399206.html](https://www.cnblogs.com/gengyi/p/6399206.html)

1. 打出前一天的时间

```php
date('Y-m-d H:i:s', strtotime('-1 day'))
```

1. echo、print、print\_r的 区别

echo 是一个语法结构。用于输出基本变量信息。print是一个函数。有返回值。print\_r是一个函数。一般用来打印复合类型信息。

1. 翻转字符【包含中文】

```php
 function strRev($str,$encoding='utf-8'){
        $result = '';
        $len = mb_strlen($str);
        for($i=$len-1; $i>=0; $i--){
            $result .= mb_substr($str,$i,1,$encoding);
        }
        return $result;
    }
```

1. 遍历一个文件夹下的所有文件和子文件

```php
function my_dir($dir) {
    $files = array();
    if(@$handle = opendir($dir)) { //注意这里要加一个@，不然会有warning错误提示：）
        while(($file = readdir($handle)) != = false) {
            if($file != ".." && $file != ".") { //排除根目录；
                if(is_dir($dir."/".$file)) { //如果是子文件夹，就进行递归
                    $files[$file] = my_dir($dir."/".$file);
                } else { //不然就将文件的名字存入数组；
                    $files[] = $file;
                }

            }
        }
        closedir($handle);
        return $files;
    }
}
```

1. 不适用第三个变量交换两个变量的值

```php
function swap (int &$a, int &$b){
     // 20 10 
    $a = $a+$b; // 30
    $b = $a-$b; //20 a
    $a = $a-$b;
}
```

1. XSS、CSRF、SQL注入

XSS 跨站脚本攻击。通常是由于没有过滤用户的输入导致的。

CSRF 跨站请求攻击。

SQL注入。用户的输入非法字符 和后端的sql组成了危险的sql语句

1. PHP实现单例模式
2. MVC的认识
3. $\_SERVER 常用字段的意思
4. cookie 和session之间的关系
5. GET和POST区别
6. 接口和抽象类的区别
7. TCP/IP HTTP
8. 进程、协程、线程
9. 进程通信的方式
10. 并发编程模型
    * 多进程
    * 多线程
    * epoll
11. epoll select  poll区别
12. 二维数组排序

## Linux

linux计划任务

在每天凌晨1点运行 a.sh文件

0 1  __ \* sh a.sh

每隔五分钟运行一次

5/ __  __ \* sh a.sh

每周一当前13：00每隔五分钟运行一次

5/ _13_  \* 1 sh a.sh

每月的1号和15号每隔两个小时执行一次

`* */2 1,15 * sh a.sh`

## mysql

1. **Myisam和innodb的差别**

存储结构。myisam一个表，三个文件。结构、数据、索引

innodb 两个文件。索引、数据保持在一个文件。

innodb支持事务、myiam不支持

innodb支持外键、支持行锁

1. **优化数据库的方法**
2. 选择正确的存储引擎
3. 选择合适的表字段类型
4. 适当的增加索引
5. 增加服务器的硬件
6. 分库分表
7. 读写分离
8. **数据库的事务**
9. **写出发帖数最多的十个人的名**

posts\(id,username,content\) id帖子序号、username 用户名、content内容

```sql
select count(id) as ct from posts group by username order by ct desc  limit 10;
```

1. **有一个数据表user需要按 uid 10，32，22，76，13的顺序检索出来**

```sql
select * from user where uid  =10 union select * from user where uid  =32 union select * from user where uid  =22 union select * from user where uid  =22 union select * from user where uid  =76 union select * from user where uid  =13
```

1. user表记录学生的信息。有uid，和name，subject表是科目。主要subject\_name,subject\_id. score表是记录学生各科的成绩，有uid,subject\_id,score\(分数\)，example\_id\(学期\)
   * 写出每个学生各科目的所有成绩的平均成绩

     ```sql
     select avg( `score`) from score group by uid
     ```

   * 查出科目id为10的，所有平均分排名前十的学生

     ```sql
     select avg(`score`) as avg_number from score group by uid subject_id having (subject_id =10 ) limit 10
     ```

   * 平均成绩大于300的学生的学号

     ```sql
     select avg(`score`) as avg_number,uid from score where avg_number > 300
     ```
2. mysql 查询一个数据库中的所有的表名

   ```sql
   select table_name 
   from information_schema.tables 
   where table_schema='当前数据库'
   ```

3. mysql 日期函数

## 算法

* 翻转数组

```php
/**
 * 反转数组
 * @param  array $arr 
 * @return array
 */
function reverse($arr)
{
    $n = count($arr);

    $left = 0;
    $right = $n - 1;

    while ($left < $right) {
        $temp = $arr[$left];
        $arr[$left++] = $arr[$right];
        $arr[$right--] = $temp;
    }

    return $arr;
}
```

* 约瑟夫环

```php
function yuesefu($n,$m) {  
    $r=0;  
    for($i=2; $i<=$n; $i++) {
        $r=($r+$m)%$i;  
    }
    return $r+1;  
}
```

* 二分查找【如何在有序的数组中找到一个数的位置】

```php
/**
 * 二分查找
 * @param  array $array 数组
 * @param  int $n 数组数量
 * @param  int $value 要寻找的值
 * @return int
 */
function binary_search($array, $n, $value)
{
    $left = 0;
    $right = $n - 1;

    while ($left <= $right) {
        $mid = intval(($left + $right) / 2);
        if ($value > $array[$mid]) {
            $right = $mid + 1;
        } elseif ($value < $array[$mid]) {
            $left = $mid - 1;
        } else {
            return $mid;
        }
    }

    return -1;
}
```

## REDIS

Memcache 该产品本身特别是数据在内存里边的存储，如果服务器突然断电，则全部数据就会丢失 单个key（变量）存放的数据有1M的限制 存储数据的类型都是String字符串类型 本身没有持久化功能 可以使用多核（多线程） Redis 数据类型比较丰富:String、List、Set、Sortedset、Hash 有持久化功能，可以把数据随时存储在磁盘上 本身有一定的计算功能 单个key（变量）存放的数据有1GB的限制

