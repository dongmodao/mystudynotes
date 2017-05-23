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
