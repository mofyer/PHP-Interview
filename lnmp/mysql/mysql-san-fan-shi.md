# 数据库范式

## mysql三范式

### 第一范式：属性原子性不可分割

第一范式是最基本的范式。如果数据库表中的所有字段值都是不可分解的原子值。

比如 在一个用户表 存在一个字段班级叫3年级2班。这个属性就不符合第一范式。这个字段可以分成3年级、2班

### 第二范式：非主键字段和主键直接关联

第二范式在第一范式的基础之上更进一层。第二范式需要确保数据库表中的每一列都和主键相关，而不能只与主键的某一部分相关（主要针对联合主键而言）。也就是说在一个数据库表中，一个表中只能保存一种数据，不可以把多种数据保存在同一张数据库表中。

比如订单表

![](https://pic002.cnblogs.com/images/2012/270324/2012040114063976.png)

在这个表中，存在订单信息和用户信息，和订单不是直接相关的

### 第三范式：消除依赖传递

如果某一属性依赖于其他非主键属性，而其他非主键属性又依赖于主键，那么这个属性就是间接依赖于主键，这被称作传递依赖于主属性。 **通俗解释就是一张表最多只存两层同类型信息**

## 反三范式

没有冗余的数据库未必是最好的数据库，有时为了提高运行效率，提高读性能，就必须降低范式标准，适当保留冗余数据。具体做法是： 在概念数据模型设计时遵守第三范式，降低范式标准的工作放到物理数据模型设计时考虑。降低范式就是增加字段，减少了查询时的关联，提高查询效率，因为在数据库的操作中查询的比例要远远大于DML的比例。但是反范式化一定要适度，并且在原本已满足三范式的基础上再做调整的
