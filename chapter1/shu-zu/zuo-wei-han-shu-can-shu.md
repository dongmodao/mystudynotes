# 一维数组

## 数组元素作为函数参数
+ “值传参”方式。

与一般的变量一样使用即可。在函数中更改值并不会对数组本身造成任何影响。函数结束后，该部分占用的内存被释放。

## 数组名作为函数参数
+ 传递的是地址。

C++中，数组名就是数组在内存中存放的首地址。用作为参数时，函数的形参和实参都应该是数组名，即函数接受的是一个地址。所以形参和实参两者公用一段内存。
形参大小不能指定，实参必须指定大小。调用时符合类型一致。

``` cpp
#include<iostream>
using namespace std;

void  sort(int x[], int n)
{
	int t, i, j;
	for (i = 0; i<n - 1; i++)
		for (j = 0; j<n - i - 1; j++)
			if (x[j]>x[j + 1])
			{
				t = x[j]; x[j] = x[j + 1]; x[j + 1] = t;
			}
}

void main(void)
{
	int a[5] = { 20, 4, 16, 8, 10 };
	sort(a, 5);
	for (int i = 0; i<5; i++)
		cout << a[i] << '\t';
	system("pause");
}
```
上述程序中，当调用了用函数名为参数的 sort 函数之后，实参 a 和形参 x 就使用了同一个内存地址，所以对 x 数组的内容修改，在函数结束之后会反映到 a 中。

# 多维数组

对于数组元素的使用是和一维数组一样的，不再赘述。

## 用多维数组名作为函数参数
+ 传递首地址
如果形参和实参都是二维数组，形参可以省略第一维大小，第二维必须与实参中的第二维维数一致。

``` cpp
#include<iostream>
using namespace std;

int max_value(int array[][4])
{
	int  i, j, max;
	max = array[0][0];
	for (i = 0; i<3; i++)
		for (j = 0; j<4; j++)
			if (array[i][j]>max)
				max = array[i][j];
	return (max);
}

void main(void)
{
	static  int  a[3][4] = { { 1, 3, 5, 7 },
	{ 2, 4, 6, 8 }, { 15, 17, 34, 12 } };
	cout << "max  is " << max_value(a) << '\t';
	system("pause");
}

```