#### 后台执行

**使用 screen 命令实现**

命令``screen command [arg1...]`` 可以打开一个新窗口执行程序，可以使用 exit 命令退出。

如果要保持该命令继续运行，则使用 ``CTRL+A 然后按 d`` 的方式暂时退出而不影响运行，重新进入时使用 ``screen -ls`` 看看都有哪些窗口正在运行，随后使用 ``screen -r port`` 恢复窗口。

参考：[让程序在远程主机后台运行 （&、nohuo、 screen）Linux 使用技巧][1]
[1]:https://blog.csdn.net/wangyezi19930928/article/details/50052947
