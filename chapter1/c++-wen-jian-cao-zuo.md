## C++ 文件操作

首先,这篇文章主要是参考了这个网址：[Cplusplus](http://www.cplusplus.com/reference/cstdio/FILE/?kw=FILE)，这是一个写了很多关于 C++ 的详细解析的网站，非常值得推荐。

### 文件的输入输出
C++ 提供了以下几个执行文件输入输出操作的类：
+ ofstream: 用于写入文件流的类 
+ ifstream: 用于读取文件流的类
+ fstream: 用于读写文件流的类

废话我也就不多说了，毕竟这个是写个自己看的，我觉得写的清楚了就好。
``` bash
#include <iostream>
#include <fstream>
#include <string>
#include <stdlib.h>
```

### 文本文件的写入
``` bash
void WriteToFile()
{
	ofstream file;				//写入使用 ofstream
	file.open("filename.txt");
	//ofstream file("filename.txt");	//该写法上述等效
	if (file.is_open())
	{
		file << "I am dongmodao." << endl;
		file << "使用 '<<' 来写入要写入的文字。" << endl;
		file.close();		//关闭文件流
		cout << "Finish Writting." << endl;
	}
	else
	{
		cout << "Fail to open this file." << endl;
	}
}
```

### 文本文件的读取
``` bash
void ReadFile()
{
	ifstream file;				// 读取使用 ifstream
	file.open("filename.txt");
	if (file.is_open())
	{
		string line = "";
		getline(file, line);		//需要使用 <string> 的头文件
		cout << line << endl;
		file.close();				//关闭文件流
	}
	else
	{
		cout << "Fail to open this file.";
	}
}
```

### 二进制方式读取文件的
打开方式一般是默认为文本方式打开，但是如果想用二进制的方式读写文件，也是可以的。

open 方法有提供两个参数的重载，除了文件名之外，还可以接受打开的方式。如下：
open (filename, mode)
``` bash
	ofstream myfile;
	myfile.open("example.bin", ios::out | ios::app | ios::binary);
```
其中，

| 参数 | 含义 |
| :------: | :------: |
| ios::in | 用于读取的打开操作 |
| ios::out | 用于写入的打开操作 |
| ios::binary | 用二进制方式打开 |
| ios::ate | 设置初始位置为文件尾 |
| ios::app | 所有写入操作在文件尾部执行 |
| ios::trunc | 文件存在则删除，不存在则新建 |

基本这些就够了，一般也不会用到更难的情况，如果有，自己翻 [Cplusplus](http://www.cplusplus.com/reference/cstdio/FILE/?kw=FILE) 再重新修行一下吧。
