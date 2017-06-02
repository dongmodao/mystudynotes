## 初涉 javascript

+ 比较运算符

第一种是 ``==`` 比较，它会自动转换数据类型再比较，很多时候，会得到非常诡异的结果；

第二种是 ``===`` 比较，它不会自动转换数据类型，如果数据类型不一致，返回 ``false``，如果一致，再比较。

建议坚持使用 ``===`` 符号进行比较。

+ 数组

可以包含任意数据类型

``` javascript
var arr = [1, 2, 'hello', null, true];
arr[0];
```

+ 对象

对象是一组有键值对组成的无序集合。可以类比于字典，键是字符串类型，值可以是任意类型。使用时为 ``对象.键``.

+ 变量

和其他语言一样，需要声明和赋值，只声明则其值为 undefined。只能声明一次，可以反复赋值为不同类型。

+ 使用 strict 模式

强制使用 ``var`` 进行声明。在javascript 代码第一行加入
> 'use strict';

+ 字符串

使用 ``${name}`` 可以把变量的值直接带入字符串当中。

``` javascript
var name = '小明';
var age = 20;
var message = `你好, ${name}, 你今年${age}岁了!`;
```
需要特别注意的是，字符串是不可变的，如果对字符串的某个索引赋值，不会有任何错误，但是，也没有任何效果。即使用 ``s[0] = 'A';`` 对 s 是没有影响的。

+ 字符串的 indexOf 与 substring
``` javascript
var s = 'hello, world';
s.indexOf('world'); // 返回7
s.indexOf('World'); // 没有找到指定的子串，返回-1
s.substring(0, 5); // 从索引0开始到5（不包括5），返回'hello'
s.substring(7); // 从索引7开始到结束，返回'world'
```

+  Map 和 Set
map 相当于字典。
声明可以用二维数组 [[key, value],[key1,value1]]作为参数，也可以是无参构造，主要的方法有 .set(key, value), .delete(key)。
``` javascript
var names = new Map();
names.set("dongmodao", 100);
```

Set 和 Map 类似，也是一组 key 的集合，但不存储 value。由于 key 不能重复，所以，在 Set 中，没有重复的 key。

+ 函数

参数可以不定义，因为在 javascript 中函数可以接受任意数量的参数。可以在内部使用 arguments[i] 来调用传入的任意参数。








