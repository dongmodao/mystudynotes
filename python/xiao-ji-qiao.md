## 小技巧

### 同行输出，如进度
``` python
for i in range(10000001):
    print("%.2f%%" % (i * 100 / 10000000), end='\r')
```
关键在于 ``end='\r'`` 的使用，效果是将光标移到该行的首位，但是注意，最后一次还是移动到了首位，所以往下的内容如果不处理会覆盖到最后的输出。以下是另一种写法，在控制台输出：
``` python
import sys
for i in range(10000):
    sys.stdout.write('{0}/10000\r'.format(i + 1))
    sys.stdout.flush()
```
其实原理也不是很复杂，就是一行结束之后不换行，回到行首，输出即可。回车符 ``\r``，回车符的作用是回到行首，这时我们再输出字符将会覆盖同一行内已存在的字符。而 Python 自身最后是默认加上了 ``\n``，使用 print 函数时，如果指定了 end 的值，那么就可以达到一些输出上的调整。所以上述的代码也不难理解了。