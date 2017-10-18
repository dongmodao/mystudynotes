## Linux 学习中的坑

1. 使用 VMware 安装 Ubuntu 不能正常上网
 看看本地的主机上的 ``VMware DHCP Service`` 和 ``VMware NAT Service`` 是否已经正常服务，如果没有，运行即可。
 
 另外的可能的原因：[VMware中安装Ubuntu虚拟机无法上网的解决方法](http://blog.csdn.net/my_xxh/article/details/50379396) 和 [Server not found problem ubuntu 17.04](https://askubuntu.com/questions/907091/server-not-found-problem-ubuntu-17-04)。可以借鉴一番。
2. 使用 root 登录
 ```shell
  sudo passwd root  
  ```
  参考：[Vmware虚拟机安装Ubuntu并设置root登陆](http://www.cnblogs.com/cursorhu/p/5803072.html) 和 [wikiHow to Become Root in Ubuntu](https://www.wikihow.com/Become-Root-in-Ubuntu)。
3. 安装 jdk
 
 参考：[How to install JDK on Ubuntu (Linux)?](https://stackoverflow.com/questions/14788345/how-to-install-jdk-on-ubuntu-linux) 和 [Ubuntu安装JDK详解](http://www.linuxidc.com/Linux/2016-11/136958.htm)。
4. 安装 eclipse
 
 参考：[Ubuntu 16.04 安装 Eclipse](http://blog.topspeedsnail.com/archives/4813) 和 [Install Eclipse IDE on Ubuntu Linux 15.04](http://linuxpitstop.com/install-eclipse-ide-on-ubuntu-linux-15-04/)。
5. 使用编辑器 vi/vim 和 gedit
 
 系统默认配置是 vi 和 gedit，vi 对于新时代的初学者可能有一点不太友好，如果不适应可以使用 gedit 或者 vi 的升级版 vim。
 这里推荐一个 vim 的简易实用使用教程：[简明 VIM 练级攻略](https://coolshell.cn/articles/5426.html)。
 
 附上一个 gedit 教程：[Ubuntu 入门操作指南](http://teliute.org/linux/TeUbt/lesson22/lesson22.html)
 
6. 配置 java 环境变量
 
 使用上面的方法安装 jdk 之后还需要配置 java 环境变量才能在 shell 里面的任意正常使用 java。我自己在配置 java 环境变量的时候遇到了不少问题。
 + 在 eclipse 中正常运行而 shell 不能正常运行
  
  检查了环境变量配置没有问题之后，发现一个文章说使用 ``java`` 命令运行的 java 文件中是不能存在包名的，解决。详情戳[如何使用命令行编译运行java程序](http://blog.csdn.net/u011043551/article/details/72571868)。
 + 配置 java 环境变量
 
  非常推荐阅读：[Java为什么要设置环境变量、JAVA_HOME](http://blog.csdn.net/u010297957/article/details/51334951)。
7. ssh 服务
 
 参考： [Ubuntu下开启ssh服务](https://hahaya.github.io/ubuntu-start-ssh-service/)

8. vnc 服务
 
 参考： [windows下通过VNC图形化访问Ubuntu桌面环境](http://blog.csdn.net/lanxuezaipiao/article/details/25552675) 和 [Windows下通过VNC远程连接Ubuntu 14.04桌面环境](https://my.oschina.net/junn/blog/401435)
 最终成功版本：[ubuntu14.04 配置VNC服务，亲测可用](http://blog.csdn.net/vbskj/article/details/52129757)
 