## bat 简单使用

1. ``>`` and ``>>``
``` shell
ping sz.tencent.com > a.txt 
ping sz1.tencent.com >> a.txt 
```
输出重定向指令，这里 ``>`` 的意思，是把前面命令得到的东西放到后面所给的地方，``>>`` 的作用，和 ``>`` 的相同，区别是把结果追加到前一行得出的结果的后面，具体的说是下一行，而前面一行命令得出的结果将保留。``>`` 会清除掉已经存在的内容。

2. ``exist`` and ``del``
``` shell
if exist c:\windows\temp\*.* del c:\windows\temp\*.* 
```
如题，存在则删除。

3. ``@``、``echo``、``::``、``pause``、``:和goto``、``%``、``if``、``call``、``type``

 + ``@``： 执行窗口中不显示它后面这一行的命令本身
 + ``echo``：on、off。是否显示后续命令
 + ``::``：注释命令，在批处理脚本中和rem命令等效
 + ``pause``：暂停
 + ``:和goto``：标签，``:``后接标签名，``goto``调到标签
 + ``%``：基本用语表示参数
 + ``if``：判断条件是否满足，满足则执行紧跟的语句，如：IF [NOT] EXIST filename do command 
 + ``call`` ：调用其他 bat，如：CALL 10.BAT 0 。调用带参数 0 的 10.BAT。
 + ``type``：列出内容，如：type input.txt
 
4. ``for``、``set``、``shift``

5. dos 命令基础

 内部命令：copy、dir、del、type、path、break、start
 外部命令：ping、net、cmd、at、sort、attrib、fc、find
 
6. ``<``、``>&``、``<&`` 
 + ``<``，输入重定向命令，从文件中读入命令输入，而不是从键盘中读入。 
 + ``>&``，将一个句柄的输出写入到另一个句柄的输入中。 
 + ``<&``，刚好和 ``>&`` 相反，从一个句柄读取输入并将其写入到另一个句柄输出中。 

7. 组合命令 ``&``、``&&``、``||``
 
 组合命令，连接处理多个命令。
 + ``&``：用来连接n个DOS命令，并把这些命令按顺序执行，而不管是否有命令执行失败。
 + ``&&``：把它前后两个命令组合起来当一个命令来用，与&命令不同之处在于，它在从前往后依次执行被它连接的几个命令时会自动判断是否有某个命令执行出错，一旦发现出错后将不继续执行后面剩下的命令。
 + ``||``：利用这种方法在执行多条命令时，当遇到一个执行正确的命令就退出此命令组合，不再继续执行下面的命令。
 
 待续。。。
 


 