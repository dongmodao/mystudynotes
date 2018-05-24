## Java JNI 编程

今天看到 Java 中的关键字时，想了解以下用法，于是就跳到了 JNI 编程中来了。。。
native 关键字用来修饰原生态的方法，方法的实现不是在本包中进行，可能是由 C/C++ 语言编写来实现的。JNI 即 Java Native Interface，是一个本机编程接口，是 Java Software Development Kit 的一部分。移植起来比较困难。

开发的主要流程如下：
 1. 在 Java 中编写用 native 修饰的方法。
 2. 使用 Javac、Java -jni 等方法生后 .h 文件。
 3. 引入 .h 文件，编写 cpp 文件来实现 .h 文件中的方法，Java 调用时就相当于执行这个实现的过程。
 4. 对 cpp 进行编译，可能过程中需要引入 jni.h 和 jni_md.h 这两个文件，位于 Java JDK 目录下的 include 文件夹中。引入，编译，生成 DLL 动态链接库。
 5. 配置 DLL。将其放于 C:\Windows\System32 或者 C:\Windows\SysWOW64 中；或将 DLL 所处文件夹加到 Path 中。
 6. 在 Java 代码中加载 DLL。使用 System.loadLibrary(DLL 名称) 来加载，一般在该对象生成前，即用 static 修饰的 {} 内进行加载。
 7. 完成。
 
 参考： 
 1. [Java 使用 JNI 调用 C++的完整流程][1]
 2. [转·Java 中 native 关键字][2]
 
[1]:https://blog.csdn.net/dinghqalex/article/details/42556647
[2]:https://blog.csdn.net/funneies/article/details/8949660