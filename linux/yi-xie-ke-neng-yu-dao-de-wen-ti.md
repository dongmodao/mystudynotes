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
 