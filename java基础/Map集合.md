# Map集合

* Map与Collection不同

* Map集合存储于取出元素的方式

* Map集合的特点

* Map集合中常用类


## Map与Collection

* Map与Collection在集合框架中属并列存在

* Map存储的是键值对

* Map存储元素使用put方法，Collection使用add方法

* Map集合没有直接取出元素的方法，而是先转成Set集合，在通过迭代获取元素

* Map集合中键要保证唯一性


## Map集合常用类

* Hashtable：线程安全，速度慢，不允许存放null键，null值，已被HashMap替代。

* HashMap：线程不安全，速度快，允许存放null键，null值。

* TreeMap：对键进行排序，排序原理与TreeSet相同。
* 例程
*练习：自定义一个可以同时存放三元素的Map集合。