# static( 静态)关键字
* static关键字：
	* 用于修饰成员（成员变量和成员函数）
* 被修饰后的成员具备以下特点：
	* 随着类的加载而加载
	* 优先于对象存在
	* 被所有对象所共享
	* 可以直接被类名调用

* 使用注意

	* 静态方法只能访问静态成员
	* 静态方法中不可以写this，super关键字
	* 主函数是静态的


#### 静态代码块
/*
静态代码块。
随着类的加载而执行。而且只执行一次。
作用：
用于给类进行初始化。
*/
		class StaticCode{
		
			static int num ;
			static{
		
			num = 10;
			// num *=3;
			System.out.println("hahahah");
			}
		
			StaticCode(){}
		
			static void show(){
				System.out.println(num);
			}
		}

		class Person{
		
			private String name;
		
			{
				//构造代码块。可以给所有对象进行初始化的。
				System.out.println("constructor code ");
				// cry();
			}
			static{
				System.out.println("static code");
			}
		
			Person(){//是给对应的对象进行针对性的初始化。
				name = "baby";
				// cry();
			}
		
			Person(String name){
				this.name = name;
				// cry();
			}
			public void cry(){
				System.out.println("哇哇");
			}
			public void speak(){
				System.out.println("name:"+name);
			}
			static void show(){
				System.out.println("show run");
			}
		}
		class StaticCodeDemo{
			static{
				// System.out.println("a");
			}
			public static void main(String[] args){
				// Person p = null;
				// p.speak();
				// Person.show();
				// Person p1 = new Person();
				// p1.speak();
				// Person p2 = new Person("旺财");
				// p2.speak();
				// new Person();
				// new StaticCode().show();
				// new StaticCode().show();
				// StaticCode.show();
				// System.out.println("b");
			}
		}


* static的特点：
	1. static是一个修饰符，用于修饰成员。
	2. static修饰的成员被所有的对象所共享。
	3. static优先于对象存在，因为static的成员随着类的加载就已经存在了。
	4. static修饰的成员多了一种调用方式，就可以直接被类名所调用 。 类名.静态成员 。
	5. static修饰的数据是共享数据，对象中的存储的是特有数据。

* 成员变量和静态变量的区别？
	1. 两个变量的生命周期不同。
		* 成员变量随着对象的创建而存在，随着对象的被回收而释放。
		* 静态变量随着类的加载而存在，随着类的消失而消失。
	2. 调用方式不同。
		* 成员变量只能被对象调用。
		* 静态变量可以被对象调用，还可以被类名调用。
	3. 别名不同。
		* 成员变量也称为实例变量。
		* 静态变量称为类变量。
	4. 数据存储位置不同。
		* 成员变量数据存储在堆内存的对象中，所以也叫对象的特有数据.
		* 静态变量数据存储在方法区(共享数据区)的静态区，所以也叫对象的共享数据.
* 静态使用的注意事项：
	1. 静态方法只能访问静态成员。(非静态既可以访问静态，又可以访问非静态)
	2. 静态方法中不可以使用this或者super关键字。
	3. 主函数是静态的。

#### 静态的使用：

静态什么时候用？

1. 静态变量。
	* 当分析对象中所具备的成员变量的值都是相同的 。
	* 这时这个成员就可以被静态修饰。
	* 只要数据在对象中都是不同的，就是对象的特有数据，必须存储在对象中，是非静态的。
	* 如果是相同的数据，对象不需要做修改，只需要使用即可，不需要存储在对象中，定义成静态的。
2. 静态函数。
	* 函数是否用静态修饰，就是该函数功能是否有访问到对象中的特有数据。
	* 简单点说，从源代码看，该功能是否需要访问非静态的成员变量，如果需要，该功能就是非静态的。
	* 如果不需要，就可以将该功能定义成静态的。当然，也可以定义成非静态，
	* 但是非静态需要被对象调用，而仅创建对象调用非静态的
	* 没有访问特有数据的方法，该对象的创建是没有意义