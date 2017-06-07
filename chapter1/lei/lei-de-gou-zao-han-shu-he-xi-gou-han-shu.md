## 构造函数
构造函数是在创建对象时，使用给定的值来将对象初始化。
可以带参数、可以重载。
``` cpp
#include<iostream>
using namespace std;
class A{
	float  x, y;
public:
	A(float a, float b){ x = a; y = b; }
	float &Getx(void) { return  x; } 	//返回 x 的引用
	void Set(float a, float b) { x = a;   y = b; }
	void Print(void) { cout << x << '\t' << y << endl; }
};
void main(void)
{
	A  a1(3, 5);
	//a1.Set(3, 5);
	cout << "a1:  ";
	a1.Print();
	a1.Getx() = 30;	//将 a1 对象中的 x 成员赋值
	cout << "changed  a1: ";
	a1.Print();
	system("pause");
}
```

## 析构函数
析构函数的功能与构造函数正好相反，是在系统释放对象前，对对象做一些善后工作。
不带参数，无返回值，无函数类型。只有一个，不能重载。
> 格式：ClassName:~ClassName(){}

``` cpp
class A{
	float  x, y;
public:
	A(float a, float b){ x = a; y = b; }
	~A(){ cout << "调用析构函数";}
	float &Getx(void) { return  x; } 	//返回 x 的引用
	void Set(float a, float b) { x = a;   y = b; }
	void Print(void) { cout << x << '\t' << y << endl; }
};
```
**在程序的执行过程中，对象如果用 new 运算符开辟了空间，则在类中应该定义一个析构函数，并在析构函数中使用 delete 删除由 new 分配的内存空间。因为在撤消对象时，系统自动收回为对象所分配的存储空间，而不能自动收回由 new 分配的动态存储空间。**

用户显式调用析构函数时，相当于调用函数，并不进行删除对象前的清理工作，可以在析构函数中定义清理工作；而系统调用析构函数时，先运行函数体，再进行清理工作。

在手动析构时，要遵循“先定义后删除，后定义先删除”的原则，避免丢失一些对象的信息。

## 使用 new 和 delete
可以使用 new 运算符来动态地建立对象。建立时要自动调用构造函数，以便完成初始化对象的数据成员。最后返回这个动态对象的起始地址。用 new 运算符产生的动态对象，在不再使用这种对象时，必须用 delete 运算符来释放对象所占用的存储空间。
``` cpp
#include<iostream>
using namespace std;
class  A{
	float   x, y;
public:
	A(float a, float b)	{ x = a; y = b; }
	A()	{ x = 0;  y = 0; }
	void  Print(void)	{ cout << x << '\t' << y << endl; }
};
void main(void)
{
	A   *pa1, *pa2;
	pa1 = new  A(3.0, 5.0);//用 new 动态开辟对象空间，初始化
	pa2 = new A;//用 new 动态开辟空间，调用构造函数初始化
	pa1->Print();
	pa2->Print();
	delete  pa1;  //用 delete 释放空间
	delete  pa2; //用 delete 释放空间
	system("pause");
}
```
用 new 运算符来动态生成对象数组时，自动调用构造函数，用 delete 运算符来释放 p1 所指向的对象数组占用的存储空间时，在指针变量的前面必须加上 []， 才能将数组元素所占用的空间全部释放。否则，只释放第 0 个元素所占用的空间。
