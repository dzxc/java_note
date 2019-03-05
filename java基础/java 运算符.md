#java 运算符

### 运算符分类
* 算术运算符
* 赋值运算符
* 比较运算符
* 逻辑运算符
* 位运算符
* 三元运算符

## 算术运算符
运算符|运算|范例|结果
---|---|---
+|正号|+3|
-|负号|b = 4;|-b=-4
+|加|5+5 | 10
-|减|6-4|2 
*|乘|3*4|12
/|除|5/5|1
%|取模|5%5|0
++|自增（前）|a=2;b=a++;| a=3;b=3
++|自增（后）|a=2; b=a++;|a=3; b=2
--|自减（前）|a=2; b=--a;|a=1; b=1
--|自减（后）|a=2; b=a--;|a=1; b=2
+|字符串拼接|"he"+"llo"|"hello"
		
		System.out.println(65); // 65
		System.out.println((char)65); // A
		System.out.println((int)'A'); // 65
		System.out.println((char)('a'+1)) // b
		System.out.println('你'+0); // 20320
		System.out.println("你"+0); // 你0

		int x = 3;
		byte b = 5;
		x  = x + b;


##### 算术运算符的注意问题
* 如果对负数取模，可以把模数负号忽略不记，如：5%-2=1。但被模数是负数就另当别论。

* 对于除号“/”，它的整数除和小数除是有区别的：整数之间做除法时，只保留整数部分而舍弃小数部分。
	 例如：int x=3510;x=x/1000*1000; x = 3000
* “+”除字符串相加功能外，还能把非字符串转换成字符串 ，
	例如：System.out.println("5+5="+5+5);// 打印结果"5+5=55" 

##  赋值运算符
##### 符号：= , +=, -=, *=, /=, %=
#### 示例：
	int a,b,c; a=b=c =3;
	int a = 3; a+=5;等同运算a=a+5;
	
	short s = 3;
	s=s+2;
	s+=2 ; // 当使用+=，-=这些运算符，编译器不回去检验两边的操作数，有可能发生异常

## 比较运算符
运算符|运算|范例|结果
---|---|---
==|相等于 | 4==3|false
!=| 不等于| 4!=3|true
<| 小于| 4<3|false
>| 大于| 4>3|true
<=| 小于等于|4<=3 |false
>=| 大于等于| 4>=3|true
instanceof | 检查是否是类对象 | "Helo" instanceof|true
##### 注意：
* 1 比较运算符的结果都是boolean型，要么是true，要么是false，运算完的结果必须是true戒者false

		System.out.println(3>2);//true
		System.out.println(3==2);//false

* 2 比较运算符“==”不能误写成“=” 


## 逻辑运算符
运算符|运算|范例|结果
---|---|---
&|AND(与)|false & true|false
&#124; |OR(或)|false &#124; true|true
^|XOR(异或)|true ^ false|true
!|NOT(非)|!true|false
&&|AND(短路)|false && true|false
&#124;&#124;|OR(短路)|false &#124; &#124; true|true

经典小题：

	// 对两个整数变量的值进行互换 (不需要第三方变量)
	int a = 3,b = 5;
	System.out.println("a="+a+",b="+b);
	
	开发时，使用第三方变量的形式，因为阅读性强。
	int c ;
	c = a;
	a = b;
	b = c;
	
	//这种方式不要用，如果两个整数的数值过大，会超出int范围，会强制转换。数据会变化。
	a = a + b; //a = 3 + 5;a = 8;
	b = a - b; //3+5-5 = 3;b = 3;
	a = a - b; //3+5-3 = 5;a = 5;
	
	// 面试的时候用。
	a = a ^ b; //a = 3 ^ 5;
	b = a ^ b; //b = (3^5)^5; b = 3;
	a = a ^ b; //a = (3^5)^3; a = 5;
	
	System.out.println("a="+a+",b="+b);

##### 注意：逻辑运算符用于连接布尔型表达式，在Java中不可以写成3<x<6，应该写成x>3 & x<6 。

#### “&”和“&&”的区别：
*  单&时，左边无论真假，右边都进行运算；
*  双&时，如果左边为真，右边参与运算，如果左边为假，那么右边不参与运算。
* “|”和“||”的区别同理，双或时，左边为真，右边不参与运算。
* 异或( ^ )与或( | )的不同之处是：当左右都为true时，结果为false

## 位运算符
位运算是直接对二进制进行运算。

运算符 |运算 |范例
---|---|---
<<| 左移| 3 << 2 = 12 ‐‐> 3*2*2=12
>>| 右移| 3 >> 1 = 1  ‐‐> 3/2=1
>>>| 无符号右移| 3 >>> 1 = 1 ‐‐> 3/2=1
& |与运算| 6 & 3 = 2
&#124; |或运算| 6 &#124; 3 = 7
^ |异或运算| 6 ^ 3 = 5
~ |反码| ~6 = ‐7


	//最有效率的方式算出2乘以8等于几？
	 System.out.println(2<<3); //位运算 

	// 对一个整数的最后一个字节，高四位和低四位进行换位。
	int num = 61;
	
	int n1 = num & 15;//低四位
	int n2 = num & (15<<4);//高四位

	int n = n1<<4 | n2>>>4; // 交换位置后填入

	System.out.println("n="+n);


异或运算中，弼一个数异或运算同一个数两次，结果还是这个数本身，如 a^b^b=a

### 位运算符的细节
---|---
<<| 空位补0，被移除的高位丢弃，空缺位补0。
>>|被移位的二进制最高位是0，右移后，空缺位补0；最高位是1，空缺位补1。
>>>| 被移位二进制最高位无论是0或者是1，空缺位都用0补。
&| 二进制位进行&运算，只有1&1时结果是1，否则是0;
&#124; | 二进制位进行 &#124;  运算，只有0 &#124;  0时结果是0，否则是1;
^|任何相同二进制位进行 ^ 运算，结果是0；1^1=0 , 0^0=0</br>不相同二进制位 ^ 运算结果是1。1^0=1 , 0^1=1

## 三元运算符
#### 格式:
* (条件表达式)?表达式1：表达式2；
* 如果条件为true，运算后的结果是表达式1；
* 如果条件为false，运算后的结果是表达式2；

#### 示例：
	 // 获取两个数中大数。
	 int x=3,y=4,z;
	 z = (x>y)?x:y; //z变量存储的就是两个数的大数

## 运算符优先级
**摘自 雪山上的蒲公英 https://www.cnblogs.com/zjfjava/p/5996666.html**
![][运算符优先级]

1. 该表中优先级按照从高到低的顺序书写，也就是优先级为1的优先级最高，优先级14的优先级最低。
 
2. 结合性是指运算符结合的顺序，通常都是从左到右。从右向左的运算符最典型的就是负号，例如3+-4，则意义为3加-4，符号首先和运算符右侧的内容结合。

3. instanceof作用是判断对象是否为某个类或接口类型，后续有详细介绍。

4. 注意区分正负号和加减号，以及按位与和逻辑与的区别
 
其实在实际的开发中，不需要去记忆运算符的优先级别，也不要刻意的使用运算符的优先级别，对于不清楚优先级的地方使用小括号去进行替代，示例代码：
      
		int m = 12;
		int n = m << 1 + 2;
		int n = m << (1 + 2); //这样更直观

这样书写代码，更方便编写代码，也便于代码的阅读和维护。

[运算符优先级]:data:image/png;base64,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