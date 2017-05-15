### 文件操作

``` python
# 1
f = open("test.txt", "w")
# 打开方式：w, r, a, 二进制文件使用 wb, rb, ab 
f.readline()
f.close()

# 2
with open("test.txt","w") as f:
	f.readline()
	...
	f.close()
	
# 3 指定字符编码打开
with open("test.txt","r", encoding='gbk') as f:
	f.readline()
	...
	f.close()

```

### 判断文件是否存在

``` python
import os

if os.path.isfile("test.txt"):
	# 存在时的操作
	...
```


#### and, or, not 的使用
在 python 中，不使用 &&, ||, ! 符号，而是使用 and, or, not 
