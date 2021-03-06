# java标识符与注释
## java标识符

### Java中的名称规范：

##### 1. 包名：多单词组成时所有字母都小写。
•  xxxyyyzzz

##### 2. 类名接口名：多单词组成时，所有单词的首字母大写。
•  XxxYyyZzz

##### 3. 变量名和函数名：多单词组成时，第一个单词首字母小写，第二
个单词开始每个单词首字母大写。
•  xxxYyyZzz

##### 4. 常量名：所有字母都大写。多单词时每个单词用下划线连接。
•  XXX_YYY_ZZZ

## 注释

### 用于注解说明解释程序的文字就是注释。

##### 提高了代码的阅读性。
* 对于单行和多行注释，被注释的文字，不会被JVM（java虚拟机）解释执行。

* 对于文档注释，是java特有的注释，其中注释内容可以被JDK提供的工具 javadoc 所解析，生成一套以网页文件形式体现的该程序的说明文档。

* 注释是一个程序员必须要具有的良好编程习惯。

* 初学者编写程序可以养成习惯：先写注释再写代码。

* 将自己的思想通过注释先整理出来，在用代码去体现。因为代码仅仅是思想的一种体现形式而已

#### Java中的注释格式：

*  单行注释
	格式： //注释文字
*  多行注释
	格式： /* 注释文字*/
*  文档注释
	格式：/** 注释文字 */