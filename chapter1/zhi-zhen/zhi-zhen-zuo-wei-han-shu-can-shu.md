## 指针变量作为函数参数

指针变量作为函数参数与变量本身作函数参数不同，变量作函数参数传递的是具体值，而指针作函数参数传递的是内存的地址。

``` C++
#include<iostream>
using namespace std;
void change1(int *p1, int *p2)		//传入指针变量的指向，*p 指向了内容 int
{
	int  t;
	t = *p1;
	*p1 = *p2;
	*p2 = t;
}
void change2(int x, int y)		//值传递，不会影响传入的变量本身的值
{  int  t;
    t=x;
    x=y;
    y=t;
}


void main(void)
{
	int  *point1, *point2, a, b;
	cin >> a >> b;
	point1 = &a;  point2 = &b;
	if (a<b)
		change1(point1, point2);
	cout << "a = " << a << ", b = " << b << endl;
	cout << *point1 << ", " << *point2 << endl;
	system("pause");
}
```

用指针变量作函数参数，在被调函数的执行过程中，应使指针变量所指向的参数值发生变化，这样，函数在调用结束后，其变化值才能保留回主调函数。函数调用不能改变实参指针变量的值，但可以改变实参指针变量所指向变量的值。



