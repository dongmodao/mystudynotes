## 容器 vector
使用 vector 需要: ``#include<vector>``，与此同时，还需要使用名字空间：``using namespace std``。

vector 在的类型是不定长的类型时，会出现一些特殊的问题，引起地址错误。

今天遇到一个问题，就是想使用 erase(int) 函数删除掉中间的一个元素，但是出现了一些问题，提示 “operator = 在 xx 类中不能使用”，我想这大概就是地址的出现了一些问题。