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
