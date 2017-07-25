## 字符编码

#### 字符

ASCII 使用 32 到 127 表示字符，32 表示空格，65 表示 "A"，可以很方便使用 7 bits 存储。当时使用的电脑大多数是 8 比特，所以还会有 1 个 bit 的剩余。32 以下的表示不可打印的字符。例如 7 使得机器产生蜂鸣声，12 让打印机更换到下一个纸张。

很多人把最后一个bit 形成的 128 - 255 用于个人目的，于是形成了各种各样混乱的标准。

ANSI(American National Standards Institute)美国国家标准协会把 128 以下的字符统一规定，作为标准，和 ASCII 码是相重合的。但是 128 之上的就有很多的处理方式，一般取决于地域。这些不同的系统使用的表就称为代码页。

在亚洲的，因为字符多达上千个，所以 8 比特已经不能满足，所以使用的是「双字节字符集」，即 DBCS("Double Byte Character Set")。有些字符存在 1 个字节中，有的存在两个字节中。
> It was easy to move forward in a string, but dang near impossible to move backwards. 
> 我的个人理解：所以往字符串中加入时比较容易，但是往后追溯却近乎不可能（比如删除的情况）。

但是还有很多人假装 1 个字节就是 1 个字符，1 个字符就只占用 8 个比特。这种情况在不使用多种语言或者不迁移到其他电脑上时问题不大，但是一旦发生，就会形成很多的混乱，计算机不一定能够理解和执行。于是 Unicode 就此诞生。

Unicode 尝试使用单一的字符集表示全球每一个合理的书写系统的字符。每个字符使用 16 个比特存储，所以可以表示最多 65536 个字符。但事实上 Unicode 表示的字符数并没有限制，已经远远超过了 665536 个。并不是每一个字符都可以压缩到两个字节中，无论如何，这是一个信念。


#### 编码

在内存中存储是使用的是 ``00 48 `` 还是 ``48 00``的方式，在最初没有统一。后来产生了 Unicode Byte Order Mark，即 Unicode 字符顺序标记，在 Unicode 字符串的开头存储 FE FF。这样在存储和解读的时候就能把所有的字节进行正确解读。

Unicode 产生了很多重复的 “00” ，很多程序员并不是很能接收，于是 ``UTF-8`` 的概念就出现了。使用了另一种方式来存储 Unicode 的代码点，0-127 的代码点使用单一字节存储，128 及其以上的代码点（code point）使用 2，3，最多 6 个字节来存储。
在英文中使用的很好，就像是使用 ASCII 一样，但是，如果大胆的使用了重音或者希腊字母等，就需要使用几个字节来存储一个单独的代码点。

传统的 Unicode 的编码方式称为 UCS-2 或者 UTF-16（使用 16 bits），但是还要指明是高位结尾还是地位结尾。还有新的 UTF-8 标准也能很好的对应英语文本和无脑程序，如果没有 ASCII 之外的东西。。。

上述信息是参考文章 [The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets (No Excuses!)][1]，如果有不清楚的，可以重新看一看。

[1]: https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/  "开发者最低限度要知道的 Unicode 和字符集知识"