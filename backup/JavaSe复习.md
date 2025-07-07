[1. java体系](https://www.cnblogs.com/cfl-yin/p/9314001.html#1F)

[2. java核心体制](https://www.cnblogs.com/cfl-yin/p/9314001.html#2F)

[3. 环境配置](https://www.cnblogs.com/cfl-yin/p/9314001.html#3F)

[4. 基础语法](https://www.cnblogs.com/cfl-yin/p/9314001.html#4F)

[5. 面向对象](https://www.cnblogs.com/cfl-yin/p/9314001.html#5F)

[6. 异常（Exception）](https://www.cnblogs.com/cfl-yin/p/9314001.html#6F)

[7. 数组（Array）](https://www.cnblogs.com/cfl-yin/p/9314001.html#7F)

[8. 基础类（常用类）](https://www.cnblogs.com/cfl-yin/p/9314001.html#8F)

[9. 输入输出 流 （I/O Stream）](https://www.cnblogs.com/cfl-yin/p/9314001.html#9F)

[10.容器/泛型 （Collection / Generic）](https://www.cnblogs.com/cfl-yin/p/9314001.html#10F)

[11. 线程 （Thread）](https://www.cnblogs.com/cfl-yin/p/9314001.html#11F)

[12.网络编程 （TCP/UDP）](https://www.cnblogs.com/cfl-yin/p/9314001.html#12F)

[13. GUI](https://www.cnblogs.com/cfl-yin/p/9314001.html#13F)

[14. Meta Data](https://www.cnblogs.com/cfl-yin/p/9314001.html#14F)

[15 正则表达式](https://www.cnblogs.com/cfl-yin/p/9314001.html#15F)

 

1. java体系


2. java核心体制
2.1 java虚拟机
2.2 java回收机制
3. 环境配置
4. 基础语法
4.1 标识符
4.1.1 什么是表示符
4.1.2 命名规则
（1) 组成

（2）开头

（3）大小写敏感，无长度限制。

（4）约定俗成：见名起意，不能与关键词重名

4.2 关键字
4.3 数据类型
4.3.1 常量
4.3.2 变量
（1）定义

本质上是内存中的一小块区域,用命令名来访问这个区域。

所以必须先声明（申请），然后赋值（填充内容）

（2）程序执行过程



 

（3）局部变量

（4）成员变量

4.3.3 枚举类型
（1）只能取特定值的一个

（2）使用enum关键字

（3）是java.lang.Enum类型



 

（4）其他用法

package com.cfl.util;

import org.apache.commons.collections.map.HashedMap;

import java.util.Map;

public enum Resouce {

_51JOB("51job", 1), ZHILIAN("zhilian", 2), DAJIE("dajie", 3),
HIATOU("haitou", 4), LAGOU("lagou", 5), SHIXIZENG("shixiseng", 6);

private String name ;

private int index ;

private Resouce(String name , int index ){
    this.name = name ;
    this.index = index ;
}

public String getName() {
    return name;
}
public void setName(String name) {
    this.name = name;
}
public int getIndex() {
    return index;
}
public void setIndex(int index) {
    this.index = index;
}
}

4.3.4 数据类型的划分


 

注意： （1）java基本数据类型长度不受系统影响 （2）float f = 12.3f 必须加f

4.3.5 基础数据类型的转换
（1）boolean 不能和其他类型相互转换

（2）容量小自动转换成容量大的。容量大的转换容量小的，必须强转,可能造成数据丢失。

Java语言提供了八种基本类型。六种数字类型（四个整数型（默认是int 型），两个浮点型（默认是double 型）），一种字符类型，还有一种布尔型。

byte：

byte数据类型是8位、有符号的，以二进制补码表示的整数；（256个数字），占1字节
最小值是-128（-2^7）；
最大值是127（2^7-1）；
默认值是0；
byte类型用在大型数组中节约空间，主要代替整数，因为byte变量占用的空间只有int类型的四分之一；
例子：byte a = 100，byte b = -50。
short：

short数据类型是16位、有符号的以二进制补码表示的整数，占2字节
最小值是-32768（-2^15）；
最大值是32767（2^15 - 1）；
Short数据类型也可以像byte那样节省空间。一个short变量是int型变量所占空间的二分之一；
默认值是0；
例子：short s = 1000，short r = -20000。
int：

int数据类型是32位、有符号的以二进制补码表示的整数；占3字节
最小值是-2,147,483,648（-2^31）；
最大值是2,147,485,647（2^31 - 1）；
一般地整型变量默认为int类型；
默认值是0；
例子：int a = 100000, int b = -200000。
long：

long数据类型是64位、有符号的以二进制补码表示的整数；占4字节
最小值是-9,223,372,036,854,775,808（-2^63）；
最大值是9,223,372,036,854,775,807（2^63 -1）；
这种类型主要使用在需要比较大整数的系统上；
默认值是0L；
例子： long a = 100000L，int b = -200000L。
long a=111111111111111111111111(错误，整数型变量默认是int型)

long a=111111111111111111111111L(正确，强制转换)
float：

float数据类型是单精度、32位、符合IEEE 754标准的浮点数；占4字节    -3.4*E38- 3.4*E38。。。浮点数是有舍入误差的
float在储存大型浮点数组的时候可节省内存空间；
默认值是0.0f；
浮点数不能用来表示精确的值，如货币；
例子：float f1 = 234.5f。
float f=6.26(错误  浮点数默认类型是double类型)
float f=6.26F（转换正确，强制）
double d=4.55(正确)
double：

double数据类型是双精度、64位、符合IEEE 754标准的浮点数；
浮点数的默认类型为double类型；
double类型同样不能表示精确的值，如货币；
默认值是0.0d；
例子：double d1 = 123.4。
boolean：

boolean数据类型表示一位的信息；
只有两个取值：true和false；
这种类型只作为一种标志来记录true/false情况；
默认值是false；
例子：boolean one = true。
char：

char类型是一个单一的16位Unicode字符；用 ‘’表示一个字符。。java 内部使用Unicode字符集。。他有一些转义字符  ，2字节
最小值是’\u0000’（即为0）；
最大值是’\uffff’（即为65,535）；可以当整数来用，它的每一个字符都对应一个数字
（3）实数，默认为double

（4）整数，默认为int

4.4 运算符和表达式
（1）



 

（2）自增，自减

（3）逻辑运算符---短路

（4）优先级



 

（5）三目运算符

4.5 分支
（1）if--else

（2）switch

 注意： java 6及以下只能探测int（或自动转为int，如：short）的值,java 7及以上可以探测swString的值
4.6 循环
4.6.1 for,while 和 do--while
（1）异同

for和while是先判断再执行
do...while是先执行一次再判断继不继续
所以for和while语句块可能一次都不执行，但是do...while至少会执行一次
(2)当循环次数不太确定，用while。

(3)continue对while和do-while影响很大

4.6.2 break 和 continue
（1） break跳出整个循环，注意不是跳出if

（2） continue 跳出本次循环，进入下一次循环

4.7 方法
4.8 变量的作用域
4.9 递归调用
5. 面向对象
5.1 编程语言的发展
 



 

5.2 面向过程的设计思想
5.3 面向对象的设计思想
5.4 对象和类的概念
5.5 类之间的关系
(1)关联

往往是类中的方法的参数和另外的类有关

（2）继承

（3）聚集和组合



 

 

（4）实现关系

5.6 对象和引用
（1）java中除了基本类型外，都叫引用类型.

5.7 java类的定义
(1) 内存解析



 

（2）类和对象的关系



 

5.8 构造函数
(1) 使用new+构造方法创建一个新的对象

（2）与类同名，无返回值

（3）初始化类

（4）执行顺序

Z

package constructor;

public class Z {
    Z(){
        System.out.println("Z");
    }
}
A

package constructor;

public class A extends Z{
    A(){
        System.out.println("A");
    }
    
    static{
        System.out.println("static");
    } 
}
main

package constructor;

public class Main {
    public static void main(String[] args) {
        A a = new A(); 
    }
}
结果

static
Z
A
5.9 对象的创建和使用
（1）内存解析



 

（2）方法重载

5.10 this关键字
5.11 package 和import
（1）默认引用java.lang

5.12 访问控制


 

5.13 类的继承
（1）java是单继承

（2）构造方法

--子类构造的过程中，必须调用基类的构造方法。

--子类构造方法可以用super显示调用基类的构造方法，不调，则默认调用无参数构造方法

--子类构造方法可以用super显示调用基类的构造方法,必须写在子类构造方法的第一行

--如果子类没有显式调用基类的构造方法，而基类又没有无参数构造方法则报错

5.14 方法的重写
（1） 重写要考虑访问限制

5.14 final关键字
5.15 Object类
（1）是所有java类的基类

（2）equals方法 （比较是否指向一个地方）

5.16 对象转型
（1）基类引用可以指向其子类

（2）基类不可访问子类新增加的成员

（3）可以使用对象instanceof类名 来判断该引用型变量所“指向”的对象是否属于该类，或其子类

（4）子类对象当基类对象来用，叫向上转型

（5）父类当子类对象来用，叫向下转型.(强制转换)

Animal a = new Animal();

a = new Dog();//

if(a instanceof Dog )
{
    Dog g = (Dog) a;//强制转换,数据仍在
}






 

 

 

5.17 多态


 

5.18 抽象类

（1）用abstract关键字来修饰一个类,这个类叫抽象类;用abstract来修饰一个方法叫抽象方法

（2）含有抽象方法的必须声明为抽象类,抽象类必须被继承。

（3）（继承了抽象类）的非抽象类,抽象方法必须被重写,（继承了抽象类）的抽象类可以不重写。

（4）抽象类不能实例化

（5）抽象方法只需声明,而不需要实现

5.19 final关键字
（1）final的值不能改变

（2）final的方法不能被重写

（3）final的类不能被继承

写类库用的比较多

5.20 接口
（1）是抽象方法和常量值的定义的集合



这是为了避免多继承的父类变量的重复，设置为静态变量，让他不属于任何类。

（2）一种特殊的抽象类，只包含常量和方法的定义,没有变量和方法实现。

6. 异常（Exception）
（1）所有异常类的根源：Throwable



 

 

（2）Error ：系统异常，无法处理

（3）Exception ：可处理可catch的错误

（4）RuntimeException ：

--频繁出现，可以不捕捉,如：被0除，下标溢出。



 

（5）必须捕捉的Excetion 如 IOException

（6）有返回值的方法，return语句在try{}中，必须先执行完finally再返回。

package exception;

public class Main {
    public static void main(String[] args) {
        int k = f();
        System.out.println(k);
    }

public static int f(){
	
	int i = 2 ;
	int j = 1 ;
	try{
		int x = i/j ;
		return 0 ;
	}catch(Exception e){
		e.printStackTrace();
	}
	finally{
		System.out.println("finally");
	}	
	return 0 ;
}
}

结果

finally
0
（7）先捕捉小的异常，再捕捉大的

（8）异常和重写

7. 数组（Array）
7.1 一维数组
（1）动态初始化

int a = new int [3];
a[0] = 1 ;
a[1] = 2 ;
1[2] = 3;
（2）静态初始化

int a = {1,2,3};

Date days []{
    new Date(1,4,2018),
    new Date(1,5,2018)
}
(3) 默认值

Date days[] = new Date[3];
System.out.println(days[0]);
结果：null

7.2 二维数组
(1) 静态初始化

int a[][] = new {{1,2,3},{3,4,5,6},{7,8,9}};
(2) 数组的声明应该按照高维到低维顺序(左到右)



 

8. 基础类（常用类）
8.1 String 和 StringBuffer
（1）String 常用方法





 



 

 

（2）StringBuffer 常用方法

 



 





 

 

 

（3）String和StringBuffer比较

--Stirng 是不可变的字符序列，修改时构建新的，是不断copy

--StringBuffer是可变的，可直接修改

8.2 包装类
8.3 Math和File
（1）Math 常用方法



 

（2）File 常用方法



 

--递归列出文件树形结构

 



 

9. 输入输出 流 （I/O Stream）
9.1 Java流式输入输出原理


 

9.2 Java流类的分类


 

 

9.3 输入/输出流类
--站在程序角度

9.3.1 InputStream
（1）组织关系



（2）基本方法



9.3.2 OutputStream
（1）组织关系



 

 

（2）基本方法

 

 

 

9.3.3 Reader
（1）组织关系



 

（2）基本方法



 

9.3.4 Writer
（1）组织关系



 

（2）基本方法



 

 

9.4 常见的节点流和处理流
--原始的管道，节点流。套在其他管道流上的，叫处理流

（1） 节点流



 

（2） 处理流



 

9.5 文件流
--例子 FileInputStream

package io;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;

public class IOMain {
    public static void main(String[] args) {
	
	FileInputStream fis = null;
	
	FileOutputStream fos = null;
	
	try {
		 fis = new FileInputStream("C:/Users/L/Desktop/test2.txt");
		 
		 fos = new FileOutputStream("C:/Users/L/Desktop/x.txt");
		 
		 int c ;
		 
		 while((c=fis.read())!=-1){
			 fos.write(c);
			 fos.flush();
		 }
		 System.out.println("ok");
		 
	} catch (FileNotFoundException e) {
		e.printStackTrace();
	} catch (IOException e) {
		// TODO Auto-generated catch block
		e.printStackTrace();
	}
}
}
--FileReader

package io;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.io.Writer;

public class IOMain2 {
    public static void main(String[] args) {
	
	FileReader fis = null;
	
	FileWriter fos = null;
	
	try {
		 fis = new FileReader("C:/Users/L/Desktop/test2.txt");
		 
		 fos = new FileWriter("C:/Users/L/Desktop/x.txt");
		 
		 int c ;
		 
		 while((c=fis.read())!=-1){
			 fos.write(c);
			 System.out.println((char)c);
			 fos.flush();
		 }
		 System.out.println("ok");
		 
	} catch (FileNotFoundException e) {
		e.printStackTrace();
	} catch (IOException e) {
		// TODO Auto-generated catch block
		e.printStackTrace();
	}
}
}
--BufferedReader

package io;

import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.io.Reader;
import java.io.Writer;

public class IOMain3 {
    public static void main(String[] args) {
	
	BufferedReader fis = null;
	
	BufferedWriter fos = null;
	
	try {
		
		 fis = new BufferedReader(new FileReader("C:/Users/L/Desktop/test2.txt"));
		 
		 fos = new BufferedWriter(new FileWriter("C:/Users/L/Desktop/y.txt"));
		 
		 String c ;
		 
		 while((c=fis.readLine())!=null){
			 fos.write(c);
			 System.out.println(c);
			 fos.flush();
		 }
		 System.out.println("ok");
		 
	} catch (FileNotFoundException e) {
		e.printStackTrace();
	} catch (IOException e) {
		// TODO Auto-generated catch block
		e.printStackTrace();
	}
}
}
9.6 缓冲流
9.7 数据流
9.8 转换流
9.9 Print流
9.9 Object流
10.容器/泛型 （Collection / Generic）
--1 1 3 6 1个图，1个类，3个知识点，6个接口

10.1 组织关系图


 

 

10.2 一个类


 

10.3 6个接口
10.3.1 Collection接口


 

10.3.2 Set
--数据对象无顺序，不可以重复（equals），可以和集合相呼应

--重写equals和hashcode,确定判断重复的条件



 

 

--JDK API中Set的容器类有HashSet，和TreeSet

10.3.3 List
--数据对象有顺序，可以重复

--JDK API中List的容器类有ArrayList，LinkList





 



 

10.3.4 Map
--键值对存储，键不可重复（覆盖）

--JDK API中Set的容器类有HashMap，和TreeMap

--基本方法



 

 

--打包，解包（强制转换）

--hashMap的实现原理（JDK7）

https://blog.csdn.net/jeffleo/article/details/54946424

--JDK7 和 JDK8 hashMap的实现原理异同

http://www.importnew.com/23164.html

--各种容器实现类的实现原理（也有hashMap）

http://wiki.jikexueyuan.com/project/java-collection/hashmap.html

10.3.5 Iterator
（1）三个方法

--hasNext() , next() , remove()





 



 

 

 

10.3.6 Comparable接口


 

 



 

--注意 实现Comparable接口，通过实现comparaTo方法，确定排序方式

10.4 衡量标准（如何选择数据结构）
--Array 读 快 改 慢

--Linked 读 慢 改 快

--Hash 两者之间

10.5 3个知识点
--增强for

--Generlic（泛型）容器声明时确定对象的类型

--打包，解包

11. 线程 （Thread）
11.1 线程的基本概念
--线程是一个程序的不同执行路径



 

（1）直接调用run方法

和普通的方法调用没有区别

11.2 线程的创建和启动
（1）继承Thread

（2）实现Runnable接口 (推荐)

11.3 线程的调度和优先级
11.4 线程的状态控制
11.4.1 状态转换图


 

11.4.1 线程控制的基本方法


 

（1）sleep方法 是一个静态方法

Thead.sleep() //当前正在执行的线程睡眠
（2）join方法

11.5 线程的同步
（1）synchronized

synchronized 关键字，代表这个方法加锁,相当于不管哪一个线程(例如线程A)，运行到这个方法时,都要检查有没有其它线程B(或者C、 D等)正在用这个方法(或者该类的其他同步方法)，有的话要等正在使用synchronized方法的线程B(或者C 、D)运行完这个方法后再运行此线程A,没有的话,锁定调用者,然后直接运行。它包括两种用法:synchronized 方法和 synchronized 块。

Java语言的关键字，可用来给对象和方法或者代码块加锁，当它锁定一个方法或者一个代码块的时候，同一时刻最多只有一个线程执行这段代码。当两个并发线程访问同一个对象object中的这个加锁同步代码块时，一个时间内只能有一个线程得到执行。另一个线程必须等待当前线程执行完这个代码块以后才能执行该代码块。然而，当一个线程访问object的一个加锁代码块时，另一个线程仍可以访问该object中的非加锁代码块。
（2）wait() 需要使用synchronized ，让访问本对象的线程（获得锁的线程）等待，释放锁

（3）notify() 一般和wait()配对使用，叫醒一个在本对象睡眠的线程。

--ProducerConsumer

package thread;

public class ProducerConsumer {
    public static void main(String[] args) {
        Repository re = new Repository();
        Producer p[] = new Producer[4];
        Customer c[] = new Customer[2];
	
	for (int i = 0; i < p.length; i++) {
		p[i] = new Producer(re);
		new Thread(p[i]).start();
	}
	
	for (int i = 0; i < c.length; i++) {
		c[i] = new Customer(re);	
		new Thread(c[i]).start();
	}
	
	
}
} --Book

class Book {
    int id ;
    
    public Book(int id) {
        super();
        this.id = id;
    }
    
    @Override
    public String toString() {
        return "book : " + id;
    }
}

--Repository

class Repository {

int index = 0 ;

Book[] book = new Book[5];



public int getIndex() {
	return index;
}

public void setIndex(int index) {
	this.index = index;
}

public Book[] getBook() {
	return book;
}

public void setBook(Book[] book) {
	this.book = book;
}

public synchronized void push(Book b){
	while(index==book.length){
		try {
			System.out.println("仓库满了，等待");
			this.wait();
		} catch (InterruptedException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
	
	this.notifyAll();
		
	book[index] =  b;
	
	index++;
} 
 
public synchronized Book pop(){
	Book b ;	

	while(index == 0){
		try {
			System.out.println("  仓库没有书，等待");
			this.wait();
		} catch (InterruptedException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
	
	this.notifyAll();
	
	System.out.println("index"+index);
	
	
	index--;
	
	b = book[index];

	return b;
}
}

--Producer

class Producer implements Runnable{

Repository repository = null;

public Producer(Repository repository) {
	this.repository = repository;
}

@Override
public void run() {
	for (int i = 0; i < 2000; i++) {
		Book b = new Book(i);
		repository.push(b);
		System.out.println("生产了"+b+"   仓库目前书的数量：" + repository.getIndex());
		
		try {
			Thread.sleep((long) (1000*Math.random()));
		} catch (InterruptedException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
}
}
--Customer

class Customer implements Runnable{

Repository repository = null;	

public Customer(Repository repository) {
	super();
	this.repository = repository;
}

@Override
public void run() {
	for (int i = 0; i < 2000; i++) {
		Book b = repository.pop();
		System.out.println("消费了"+b+"  仓库目前书的数量：" + repository.getIndex());
		try {
			Thread.sleep((long) (1000*Math.random()));
		} catch (InterruptedException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
}
}

注意：

	while(index==book.length){
		try {
			System.out.println("仓库满了，等待");
			this.wait();
		} catch (InterruptedException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
要用while不用if，否则被叫醒后，不会再判断是否index==book.lengt，而是继续往下执行。

12.网络编程 （TCP/UDP）
--网络编程！=网站编程

12.1 网络基础
12.2 TCP/IP协议
12.3 IP地址
12.4 Socket通信
（1）TCP/UDP

13. GUI
14. Meta Data
15 正则表达式
import java.io.*;
import java.util.Scanner;
import java.util.regex.*;

public class Example {
    public static void main( String args [])
    {
            Scanner read = new Scanner (System.in);
            
            System.out.println("Please input String :");
            
            /**********************   
            *    X+ 表示X出现了1次或多次
            *    X？ 表示出现了0次或1次
            *    \56表示小数点
            *    X{n} 表示恰好出现n次
            *    X{n,} 表示X出现次数>=n
            *    XY表示X的后缀为Y
            *    X|Y 表示X或Y
            *    \\p{Alpha}表示字母
            *    \\w  表示可用于标识符的字符
            *    [a-z&&[def]] 代表 d e f中任意一个 （交）
            *    [a-f&&[^bc]]  代表 adef 的差 
            *    
            *    \\d表示0-9中任何一个数字
            */
            
//    	    String s = "(http://|www)\56?\\w+\56{1}\\w+\56{1}\\p{Alpha}+";  //筛选网址
            
//    	    String s  = "[abc]";   //[]表示其中任何一个   
            
//    	    String s ="[a-d]"; //  a-d 表示从a到d中一个
            
//例14    	String s ="[0-9]+\56?[0-9]*";  //筛选出字符串中的浮点数

            //String s ="1{3,4}"; //  注意贪婪匹配，输入1111 111 第一次1111 第二次111
            
//    	    String s ="a1*"; //        注意贪婪匹配，输入1111 111 第一次1111 第二次111
            
            String s ="P=\\{+.+\\}+";
            
            Pattern pattern = Pattern.compile(s);   //匹配条件
                        
            Matcher matcher = pattern.matcher(read.nextLine());  //要匹配的目标字符串
            

            
            while(true)
            {
                if (matcher.find())
                {

                    System.out.printf("%s can find ! , %d--%d\n",matcher.group(),matcher.start(),matcher.end());
                    
                    break;
                }
                else 	
                {
                    break;  	  		
                }
            }
//         	System.out.println("字母个数为： "+n);

    
    }	  	
                
    }