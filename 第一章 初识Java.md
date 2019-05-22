# 第一章 初识Java




# 第一节 Java的历史与特点

## 1.1 Java历史

- ***J2SE*** 	Java的标准版本 (Java2 Standard Edition) 定位在客户端，**<font color="red">主要用于桌面应用软件的编程</font>**
- ***J2ME***	 (Java2 Micro Edition)**<font color="red">主要应用于嵌入式系统开发</font>**，如手机和PDA的编程
- ***J2EE*** 	企业版本(Java2 Enterprise Edition)定义在服务器端Java2的企业版，**<font color="red">主要用于分布式网络程序的开发，如电子商务网站</font>**

> 1991年，Sun公司的Green项目，Oak<br/>
> 1995年，推出Java测试版<br/>
> 1996年，JDK1.0  <br/>
> 1997年，JDK1.1<br/>
> 1998年，JDK1.2，大大改进了早期版本的缺陷，是一个革命性的版本，更名为Java2<br/>
> 1999 Java被分成J2SE、J2EE 和J2ME，JSP/Servlet技术诞生<br/>
> 2004年，J2SE 5.0 (1.5.0)  Tiger老虎.为了表示这个版本的重要性，J2SE1.5更名为J2SE5.0。<br/>
> 2006年，J2SE 6.0 (1.6.0)  Mustang野马.此时，Java的各种版本被更名，取消其中的数字"2"：J2EE更名为Java EE,    J2SE更名为Java SE，J2ME更名为Java ME<br/>
> 2009年4月20日甲骨文收购Sun公司，交易价格达74亿美元<br/>
> 2011年，JavaSE7.0<br/>
> 2014年 ，JavaSE8.0<br/>
>
> 2005 JavaOne大会召开，Sun公司公开Java SE6。此时，Java的各种版本被更名，取消其中的数字"2"：J2EE更名为Java EE, J2SE更名为Java SE，J2ME更名为Java ME<br/>





## 1.2 Java特点

- **<font color="red">Java是跨平台的</font>**
- - Java程序的跨平台主要是指字节码文件可以在任何具有Java虚拟机的计算机或者电子设备上运行，Java虚拟机中的Java解释器负责将字节码文件解释成为特定的机器码进行运行。
- **Java是简单的**
- - 不再有#include 和#define 等预处理功能
  - 不再有struct,union及typedef
  - 不再有函数、
  - 不再有指针、不再有多重继承
  - 不再有goto      
  - 不再有操作符重载(Operatior Overloading)
  - 不再有全局变量           取消自动类型转换,要求强制转换
  - 不再有手动内存管理
- **Java是安全的**
- - Java取消了强大但又危险的指针。由于指针可进行移动运算，指针可随便指向一个内存区域，而不管这个区域是否可用，这样做是危险的，因为原来这个内存地址可能存储着重要数据或者是其他程序运行所占用的， 并且使用指针也容易数组越界。
  - Java提供了自动内存管理机制，由垃圾回收器在后台自动回收, 
  - Java在字节码的传输过程中使用了公开密钥加密机制(PKC)。
  - 而在运行环境提供了四级安全性保障机制：
  - 字节码校验器 -类装载器 -运行时内存布局 -文件访问限制
- **Java是完全面向对象的**
- - Java和C++都是面向对象语言。也就是说，它们都能够实现面向对象思想（封装，继承，多态）。	
  - 由于C++为了照顾大量C语言使用者而兼容了C，使得自身仅仅成为了带类的C语言，多少影响了其面向对象的彻底性！
  - Java则是完全的面向对象语言，它句法更清晰，规模更小，更易学。它是在对多种程序设计语言进行了深入细致研究的基础上，据弃了其他语言的不足之处，从根本上解决了c++的固有缺陷。
- **Java是健壮的**
- - Java的强制类型机制、异常处理、垃圾的自动收集等是Java程序健壮性的重要保证。
  - 对指针的丢弃是Java的明智选择。
  - Java的安全检查机制使得Java更具健壮性。 	

# 第二节 **Java跨平台原理**

1.C/C++语言都直接编译成针对特定平台机器码。如果要跨平台，需要使用相应的编译器重新编译。 

2.Java 源程序（.java）要先编译成与平台无关的字节码文件(.class)，然后字节码文件再解释成机器码运行。解释是通过Java虚拟机来执行的。 字节码文件不面向任何具体平台，只面向虚拟机。 

3.Java 虚拟机是可运行 Java 字节码文件的虚拟计算机。不同平台的虚拟机是不同的，但它们都提供了相同的接口。 

4.Java语言具有一次编译，到处运行的特点。就是说编译后的.class可以跨平台运行，前提是该平台具有相应的 Java虚拟机。但是性能比C/C++要低。

5.Java的跨平台原理决定了其性能没有C/C++高 



## 2.1 Java运行过程

Java程序的运行分为两步：先编译再解释执行

通过“编译器”将Java源程序编译成Java 字节码文件（.class）(字节码文件采用结构中立的中间文件格式)

通过不同的“虚拟机”将Java字节码文件解释为对应机器语言并执行 

## 2.2 字节码文件bytecode

字节码文件是 .class文件  二进制文件
格式中立、平台无关的二进制文件
是编译的产物，是解释的原料

## 2.3 Java虚拟机 JVM

JVM是Java Virtual Machine（Java虚拟机）的缩写

JVM是一种用于计算设备的规范，它是一个虚构出来的计算机，是通过在实际的计算机上仿真模拟各种计算机功能来实现的。

JVM就是一个虚拟的用于执行bytecodes字节码的计算机

Java虚拟机是Java最核心技术，也是跨平台的基础。

Java语言使用Java虚拟机屏蔽了与具体平台相关的信息，使得Java语言编译程序只需生成在Java虚拟机上运行的目标代码（字节码），就可以在多种平台上不加修改地运行。

Java虚拟机在执行字节码时，把字节码解释成具体平台上的机器指令执行。这就是Java的能够“一次编译，到处运行”的原因

## 2.4 JDK、JRE、JVM的区别联系

**<font color="red">JDK</font>**

Java Development Kit

针对Java开发员的产品，是整个Java的核心，包括了Java运行环境JRE、Java工具和Java基础类库。

**<font color="red">JRE</font>**

Java Runtime Environment

是运行Java程序所必须的环境集合，包含JVM标准实现及Java核心类库。

**<font color="red">JVM</font>**

Java Virtual Machine

解释运行Java字节码文件，跨平台的核心

联系：**JDK 包含JRE，JRE包含JVM。**

我们想要运行一个已有的Java程序，那么只需安装 JRE 即可。

我们想要开发一个全新的Java程序，那么必须安装 JDK

## 2.5 Java跨平台和C跨平台的区别

Java：一次编译，到处运行     C：多次编译，到处运行

在互联网情况下，平台各异，Java的跨平台更具有优势

Java可以跨所有平台吗：要看有没有提供并安装相应的虚拟机

Java的运行速度没有C语言快

Java需要将class文件解释成机器码再执行；C执行执行机器码  

- 第一，C语言是编译执行的，编译器与平台相关，编译生成的可执行文件与平台相关；
- 第二，Java是解释执行的，编译为中间码的编译器与平台无关，编译生成的中间码也与平台无关（一次编译，到处运行），中间码再由解释器解释执行，解释器是与平台相关的，也就是不同的平台需要不同的解释器.


# 第三节 DOS命令入门

- **DOS操作系统**
- - DOS是英文"Disk Operating System"的缩写,其中文含意是"磁盘操作系统".
- - DOS是单用户、单任务的操作系统.
- - Microsoft公司推出的操作系统。
- **DOS命令**
- - 是DOS操作系统的命令，是一种面向磁盘的操作命令，
- - 主要包括目录操作命令、磁盘操作命令、文件操类命令和其它命令
- - 不区分大小写。

## 3.1 掌握三个命令

DIR(Directory):   显示目录

CD(Change Directory):   改变或显示当前目录

CLS（clear screen）：清除屏幕

## 3.2 掌握三个操作

切换盘符：：快速换盘符，例如： d: 就是切换到D盘

Tab ：自动补齐键

↑ ↓ ：查看历史语句



## 3.3 了解四个命令

MD(Make Directory):  建立子目录

RD(Remove Directory):   删除子目录

Copy  复制文件

Del （delete）删除文件

Window中文件夹（子文件夹）,在DOS称为目录（子目录），

## 3.4 熟悉window下操作

查看某个文件夹下的子文件夹和文件   dir---directory  file  /p  /w

新建文件夹  md   make directory

删除文件夹  rd  remove directory（目录必须是空的）

改变当前的文件夹  cd  change directory  cd..(Tab键的使用)



## 3.5 文件复制和删除

Copy  源文件   目的文件

copy d:\log.txt  d:\myjava\log.txt

copy \log.txt log2.txt



## 3.6 文件的删除

Del  log.txt

Del *.*  删除当前目录下所有文件（需要确认是否删除）

# 第四节 Java程序入门

Java是严格区分大小写的语言。

## 4.1 代码编写

> 代码编写: 程序员编辑代码并保存在磁盘上

.java 源程序  源代码

​	  1.定义一个类  Test

​	  2.定义一个方法  main  执行的入口

​	  3.编写语句  输出一句话

​      注释：描述性文字，不参与编译

------

Java程序源文件的命名不是随意的，Java文件的命名必须满足如下规则。

- Java程序源文件的扩展名必须是.java，不能是其他文件扩展名。
- 在通常情况下，Java程序源文件的主文件名可以是任意的。但有一种情况例外：如果Java程序源代码里定义了一个public类，则该源文件的主文件名必须与该public类（也就是该类定义使用了public关键字修饰）的类名相同。

由于Java程序源文件的文件名必须与public类的类名相同，因此，**<font color="red">一个Java源文件里最多只能定义一个public类。</font>**

> **注意**:
>
> 1.一个Java源文件可以包含多个类定义，但最多只能包含一个public类定义；
>
> 如果Java源文件里包含public类定义，则该源文件的文件名必须与这个public类的类名相同
>
> 2.虽然Java源文件里没有包含public类定义时，这个源文件的文件名可以是随意的，但推荐让Java源文件的主文件名与类名相同，这可以提供更好的可读性。
>
> 通常有如下建议：一个Java源文件只定义一个类，不同的类使用不同的源文件定义。让Java源文件的主文件名与该源文件中定义的public类同名。

**<font size="6">常见错误和注意事项</font>**

1. 每个语句都使用分号结束，必须是英文;
2. 如果class使用public修饰，要求类名和文件名相同
3. 区分大小写
4. main方法是程序执行的入口，有固定的写法
5. 注意代码缩进，提高可读性
6. 注释：单行注释  多行注释 文档注释
7. println()中双引号的内容原样输出
8. 区分大小写 String  System

## 4.2 编译阶段

> 编译器创建class字节码文件

进入java文件所在目录，执行命令：javac  Welcome.java .编译时必须加上扩展名.java。

 **.java----.class  编译器  javac.exe  compile 编译**

- **错误1：'javac' 不是内部或外部命令，也不是可运行的程序或批处理文件。**
  - 原因：javac.exe不在当前目录下
  - 解决1：将当前目录变成javac.exe所在的目录  D:\Java\jdk1.8.0_161\bin
  - 解决2：如果在当前目录下找不到javac.exe，就会到某个制定的目录下查找； 定义一个环境变量path  
- **错误2：javac: 找不到文件: Test.java**
  - 解决：需要指明Test.java的完整路径 javac d:\myjava\Test.java
  - 编译 的时候必须是  javac Test.java  不能省略扩展名
- **错误3：找不到或无法加载主类 Test.class**
  - 原因：class不写
- **错误4：找不到或无法加载主类 Test**
  - 原因：当前目录下没有Test.class
  - 解决方法：配置classpath，.;d:/myjava  首先在当前目录查找，找不到，自动到指定目录下寻找

## 4.3 执行阶段

进入java文件所在目录，执行命令：java  Welcome

运行的是类而非class文件，所以类名后不能加扩展名.class

**解释器或者虚拟机 （解释器是虚拟机的一部分）**

​		错误: 找不到或无法加载主类 Test.class

​		解决：java Test  而不是  java Test.class

## 4.4 扩展

 **1.配置classpath**

​		  classpath   .;d:\myjava

**2.path的另外一种配置方式**

​		 JAVA_HOME   D:\Java\jdk1.8.0_161

​		 PATH  %JAVA_HOME%\bin  ==============>D:\Java\jdk1.8.0_161\bin

**3.path和classpath区别**

​		  javac Test.java

​		  java Test

​		  path:javac、java在哪里

​		  classpath：Test 字节码文件在哪里

**4.Java_HOME**

​          便于重用环境变量，利用后期修改	 

**5.println和print的区别**

​          换行否  line

**6.转义字符**

​    \n  换行

​    \t  tab

**7.一个文件可以有多个类class吗？可以**

​    但是最多只能有一个类是public的

​    编译之后，会生成多个class文件

**8.反编译**

​    编译  .java----.class

​    反编译  .class----.java

​    注释不参与编译操作

**9.注释**

​    作用：说明性的文字，不参与编译；将某些代码注释，将不再执行，程序调试的常用方法；

​    类型：单行注释  多行注释  文档注释

# 第五节 反编译

**编译 compile**

源代码----->class

**反编译 decompile**

class---->源代码

**反编译软件**

jd-gui.exe

**<font color="red">因为编译的时候不会对注释进行处理，所以反编译时不可能得到注释</font>**
