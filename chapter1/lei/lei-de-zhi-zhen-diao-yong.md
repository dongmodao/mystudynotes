## 利用类的指针引用对象
使用箭头符号 -> 进行引用。
``` cpp
#include<iostream>
using namespace std;
class A{
	float  x, y;
public:
	float Sum(void) { return  x + y; }
	void Set(float  a, float  b) { x = a;	y = b; }
	void Print(void) { cout << "x=" << x << '\t' << "y=" << y << endl; }
};
void main(void)
{
	A a1, a2;
	A *p;		//定义类的指针
	p = &a1;	//给指针赋值
	p->Set(2.0, 3.0);    //通过指针引用对象的成员函数
	p->Print();
	cout << p->Sum() << endl;
	a2.Set(10.0, 20.0);
	a2.Print();
	system("pause");
}
```
## 返回私有成员的引用!
返回引用类型的成员函数(可以返回私有数据成员的引用)
可以对被返回的指针进行操作，达到更改对象的目的
``` cpp
#include<iostream>
using namespace std;
class A{
	float  x, y;
public:
	float &Getx(void) { return  x; } 	//返回x的引用
	void Set(float a, float b) { x = a;   y = b; }
	void Print(void) { cout << x << '\t' << y << endl; }
};
void main(void)
{
	A  a1, a2;
	a1.Set(3, 5);
	cout << "a1:  ";   	a1.Print();
	a1.Getx() = 30;	//将a1对象中的x成员赋值
	cout << "changed  a1: ";
	a1.Print();
	system("pause");
}
```
## this 指针
当对一个对象调用成员函数时，编译程序先将对象的地址赋给this指针，然后调用成员函数，每次成员函数存取数据成员时，也隐含使用this指针。
常用于判断是否是类实例自身。