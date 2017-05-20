## 指针变量作为函数参数

指针变量作为函数参数与变量本身作函数参数不同，变量作函数参数传递的是具体值，而指针作函数参数传递的是内存的地址。

``` C++
#include<iostream>
using namespace std;
void change(int *p1, int *p2)		//更改指针指向的位置
{
	int  t;
	t = *p1;
	*p1 = *p2;
	*p2 = t;
}
void main(void)
{
	int  *point1, *point2, a, b;
	cin >> a >> b;
	point1 = &a;  point2 = &b;
	if (a<b)
		change(point1, point2);
	cout << "a = " << a << ", b = " << b << endl;
	cout << *point1 << ", " << *point2 << endl;
	system("pause");
}
```

