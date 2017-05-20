## 变量的指针与指针变量

变量的指针是地址
指针变量是保存地址的变量，只保存地址，不接受其他类型
'*' 在语句中表示指向， '&' 表示取地址
``` c++
int i;
int j = 0;
int *i_point = &i;	//取 i 的地址给 i_point 指针变量
*i_point = 3;		//把 3 赋值到 i_point 指针变量指向的地址
i_point = &j;		//指针变量的赋值，指针变量保存 j 的地址
```
## 指针变量的引用
``` c++
void main(void)
{
	int a, b;
	int *p1, *p2;
	p1 = &a; p2 = &b;
	*p1 = 10; *p2 = 100;					//通过指针修改变量的值
	cout << a << '\t' << b << endl;
	cout << *p1 << '\t' << *p2 << endl;		//指针变量的引用
	system("pause");
}  
```

## 优先级
++, - -,  * 优先级相同，都是右结合性。
``` c++
#include<iostream>
using namespace std;

void main(void)
{
	// 访问其他位置，可能会报错
	int a = 3, *p;
	p = &a;
	cout << (*p)++ << endl;			// (*p)++, 取 p 指向的内容让后 ++		3	a = 4
	cout << a << endl;
	cout << p << endl;	
	cout << &a + 1 << endl;
	cout << "--------------------" << endl;
	a = 3;
	cout << *p++ << endl;			// *p++, 取 (*p), p++(即p = p + 1)		3	a = 3
	cout << a << endl;
	cout << p << endl;				// 指向了 a 的下一个地址
	cout << &a + 1 << endl;
	cout << "--------------------" << endl;
	a = 3;
	cout << ++*p << endl;			// (*p) = (*p) + 1						地址  a = 4
	cout << a << endl;
	cout << p << endl;
	cout << &a + 1 << endl;
	cout << "--------------------" << endl;
	a = 3;
	cout << *++p << endl;			// 即 *(++p) ,p = p + 1, *p				下个地址的值 a = 3
	cout << a << endl;
	cout << p << endl;
	cout << &a + 1 << endl;
	system("pause");
}
```