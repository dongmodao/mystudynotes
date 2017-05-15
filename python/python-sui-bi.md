文件操作

``` python
f = open("test.txt", "w")
打开方式：w, r, a, 
f.readline()
f.close()
```

判断文件是否存在
``` python
import os

if os.path.isfile("test.txt"):
	# 存在时的操作
	...
```


and, or, not 的使用
