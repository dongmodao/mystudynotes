## 函数参数

python 中使用可变参数的函数有以下方法：

1. 使用 ``*`` 符号标记，如``*args``，表示可变参数，传入内部时是元组形式。
 ``` python
 def test1(*args):
    print(type(args))  # <class 'tuple'>
    print(args)        # ('c', 'd')

 test1('c', 'd')
 ```
2. 使用 ``**`` 符号，如``**kwargs``(keyword arguments)，传入内部时是字典形式，所以在调用的时候需要用关键字表示，如 foo(arg1=value1, arg2=value2)。如下
 ``` python
 def test2(**kwargs):
    print(kwargs)           # {'d': 2, 'a': 1}
    print(type(kwargs))     # <class 'dict'>
    a = kwargs['d']
    print(a)                # 2

 test2(d=2, a=1)
 ```
 
 更优雅的用法，比如：
 ``` python
 import pymysql
 # 数据库信息
 db_conf = {
     'host':'localhost',
     'port':3306,
     'user':'root',
     'password':'xxxxxx',
     'db':'xxx',
     'charset':'utf8'
 }
db_con = pymysql.connect(**db_conf) 
 ```
参考：
[Python 优雅的使用参数 - 可变参数（\*args & \**kwargs)](1)

[1]: https://n3xtchen.github.io/n3xtchen/python/2014/08/08/python-args-and-kwargs