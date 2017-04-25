## C++ 文件操作

首先,这篇文章主要是参考了这个网址：[Cplusplus](http://www.cplusplus.com/reference/cstdio/FILE/?kw=FILE)，这是一个写了很多关于 C++ 的详细解析的网站，非常值得推荐。

### 文件的输入输出
C++ 提供了以下几个执行文件输入输出操作的类：
+ ofstream: 用于写入文件流的类 
+ ifstream: 用于读取文件流的类
+ fstream: 用于读写文件流的类

废话我也就不多说了，毕竟这个是写个自己看的，我觉得写的清楚了就好。

### 文本文件的写入
``` bash
void WriteToFile()
{
	ofstream file;
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
	ifstream file;
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

### 二进制文件的读取

