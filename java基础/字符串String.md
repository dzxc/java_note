# String类

* 字符串是一个特殊的对象。

* 字符串一旦初始化就不可以被改变。

* String str = “abc”；

* String str1 = new String(“abc”);
	* 有什么区别 ？

## String类部分方法
* char charAt(int index)

* int length()

* char[] toCharArray();

* int indexOf(String str);

* boolean endsWith(String str);

* String[] split(String reg);

* String substring(int index);

* String(char[] arr);


## StringBuffer
* 字符串的组成原理就是通过该类实现的。

* StringBuffer可以对字符串内容进行增删。

* StringBuffer是一个容器。

* 很多方法与String相同。

* StingBuffer是可变长度的。


## StringBuffer特有方法
* StringBuffer append(int x);

* StringBuffer delete(int start, int end );

* StringBuffer insert(int index,String str);

* StringBuffer reverse();

* JDK1.5出现一个StringBuilder，区别是StringBuffer是同步的，StringBuilder是非同步的。

