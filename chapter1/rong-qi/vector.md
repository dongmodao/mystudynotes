## 容器 vector
使用 vector 需要: ``#include<vector>``，与此同时，还需要使用名字空间：``using namespace std``。

vector 在的类型是不定长的类型时，会出现一些特殊的问题，引起地址错误。

今天遇到一个问题，就是想使用 erase(int) 函数删除掉中间的一个元素，但是出现了一些问题，提示 “operator = 在 xx 类中不能使用”，我想这大概就是地址的出现了一些问题。

vector 为了方便快速的随机查找，使用的是连续的内存进行存储，即一个元素接着一个元素的位置进行存储，当预留的存储空间不够使用时，被迫面临着重新开辟面临空间、复制元素的情况。具体介绍可以看这篇博文：「[vector的内存释放](http://www.cnblogs.com/summerRQ/articles/2407974.html)」。

其他的容器介绍可以看这个博文：「[c++中容器总结](http://6924918.blog.51cto.com/6914918/1275726)」。
