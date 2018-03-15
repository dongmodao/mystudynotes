1.1.1 基础的基础

 文件名和类名一致。HelloWorld.java:

 ``` java
 public class HelloWorld {
     public static  void main(String[] args){
         System.out.println("Hello World.");
     }
 }
 ```
  String[] args 表示一个数组，通过 ``args[i]``调用对应参数，可用 ``String... args`` 代替。

 一些简单的术语：
  + JDK(Java Development Kit):Java 开发工具包，开发 Java 程序的程序员使用的软件。
  + JRE(Java Runtime Environment):Java 运行时环境， 运行 Java 程序的用户使用的软件。
  + SDK(Software Development Kit):软件开发包，一些被软件工程师用于为特定的软件包、软件框架、硬件平台、操作系统等创建应用软件的开发工具的集合。
  + JVM(Java Virtual Machine):Java 虚拟机，实现平台无关的关键，虚拟计算机，通过实际在计算机上仿真模拟各种计算机功能来实现。
  + DAO(Data Access Object):数据访问接口。数据库访问中使用。
 
1.1.2 基础语法
 
 几个概念：对象、类、方法、实例。对象是类的一个实例，类是对象的抽象，具有行为和状态，方法就是类的行为，实例是类的具体化例子，对象的状态由实例变量的值决定。
 
 Java 程序编写基础：大小写敏感，类名首字母应该大写，随后每个单词首字母应该大写，方法名应以小写字母开头，随后单词首字母大写，``.java`` 源文件名与类名一致，否之编译错误，程序主入口为 public static void main(String[] args) 方法。
 
 标识符包括类名、变量名、方法名，应以 A-Z 或者 a-z、美元符号 $ 、下划线 _ 开始，随后可以包括前面几种和数字等字符组合作为标识符。关键词不能作为标识符，大小写敏感。
 
 修饰符主要修饰类中方法和属性，分类为访问控制修饰符（default、public、protected、private）和非访问控制修饰符（final、abstract、strictfp），具体后面讨论。
 
 变量包括：局部变量、类变量（静态变量）、成员变量（非静态变量）。
 
 数组时存储在对上的对象，可以保存多个同类型的变量。Java 5.0 之后引入了枚举，限制变量只能是预先设定的值。
 
 Java 关键字和其他面向对象程序的关键字有很多时一样的，对于那些不再赘述，比较不同的是：extends（表示继承于）、final（表示在使用区域内不可更改这个引用，不能再次初始化等，和 static 一起使用则作为常量）、implements（实现接口 XX）、native（本地，原生方法，非 Java 实现）、strictfp（严格，精准）、synchronized（线程间同步）、transient（短暂）、volatile（易失去、频繁更改，禁止指令重排序，写的新值对于其他线程立即可见）、instanceof（实例）、assert（断言表达式是否为真）、import（引入）、package（包），super（父类、超类）、this（本类）。
 
 继承，一个类想有已有类的属性或方法，可以继承已有类，减少代码量，可以重用已有类方法和属性，不用重写，减少代码。接口可以理解为对象间相互通信的协议，只定义派生类所需方法，实现由派生类负责。
 
 注意 Java 代码的编程规范以及注释规范。可以参照 [Java 编程风格指南](https://pangxuan2010.gitbooks.io/java-coding-style-guidelines/content/)。
 
 

 

