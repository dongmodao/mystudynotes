## C++ 类型转换

字符串转数值型
**string to double: **``int a = atof(str.c_str())``

``` cpp
string temp = "1000";
int a = atof(temp.c_str())
```


数值型转字符串
**double/int to string**
``` cpp
#include <sstream>
using namespace std;
int main()
{
int d = 10;
stringstream temp;
temp << d;    //将数值类型写入流
string rst = temp.str();    //转换
cout << rst << endl;
}
```


**注意：在 C 中**

如果使用 atof() 函数，应该要添加
``` c
#include <stdlib.h>
```
否则得到的数据可能会出现问题。

## 关于输出小数点

在 c++ 中使用
``` cpp
cout << setprecision(10) << 100.1234567890; //选择显示小数点后10位
```

在 MATLAB 中，使用科学计数法时，用命令
``` bash
format long e
```
来表明显示更长的位数。也可以使用
``` bash
'%20.15g' //来表明长度20，小数位15位，科学计数法中
```