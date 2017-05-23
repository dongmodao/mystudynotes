## 头文件
使用头文件的好处在于：
1. 代码可读性强
2. 声明与定义分开
3. 大程序的结构更清晰

如何编写头文件？示例如下：
**头文件： testcode.h**
``` cpp
#ifndef POINT_H		//用于判断是否已经调用了该头文件，避免重复调用错误  #define 保护
#define POINT_H

class Point
{
private:
	double x;
	double y;
public:
	Point(double a, double b);		//声明构造函数
	double GetX();							//声明各类函数
	double GetY();
	void Print();
};
#endif				//结束 ifndef
```

**cpp 文件： Point.cpp**
``` cpp
#include "testcode.h"
#include<iostream>
using namespace std;
Point::Point(double a, double b)
{
	this->x = a;
	this->y = b;
}
double Point::GetX()
{
	return this->x;
}
double Point::GetY()
{
	return this->y;
}
void Point::Print()
{
	cout << "x = " << x << "\ty = " << y << endl;
}
```

**运行 main 文件内容**
``` cpp
#include<iostream>
#include "testcode.h"
using namespace std;
void main(void)
{
	Point a(10, 20);
	a.Print();
	system("pause");
}
```