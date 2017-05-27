## 委托与事件
委托和事件是 C# 中一个比较重要的部分。最近小组作业中使用到了它们，今天自己写的时候遇到了小问题，于是也就稍微探究了一下。

**实现的基本方法**
``` csharp
// (1) 定义委托
internal delegate void myHandler(int a, int b);
// (2) 定义事件
internal event myHandler myevent;
// (3) 注册事件
myevent += myFunction;
// (4) 实现方法
void myFunction(int a, int b)
{...}
```

**个人理解**
委托相当于获得了一个函数的指针。可以在本类中调用其他类的函数，只要这个委托可以在其他类中注册；同时，在实现上，这个所谓的其他类的参数也可以被使用，这也是委托和事件的方便之处。