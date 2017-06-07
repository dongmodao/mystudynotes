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
