# 数组

数组是一组包含有序元素的集合。这里的数组和PHP中的数组不一样。php的数组，是一个HashTable。

数组的特点

* 元素在内存中的顺序是连续的
* 数组里面的元素的数据类型都是一样的。就是一个数组不能存储两个类型
* 数组的下标是整形。

```text
char a[5]  = "hello";
```

![5ae95daa1d834](https://i.loli.net/2018/05/02/5ae95daa1d834.jpg)

数组的几种操作

* find\|delete 查找对应元素 时间复杂度是O\(n\). 根据下标查询，时间复杂度是O\(1\)

