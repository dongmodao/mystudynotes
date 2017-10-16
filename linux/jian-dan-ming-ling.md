## 简单命令

clear		清屏

mkdir		创建目录			mkdir $HOME/testFolder

cd 			切换目录			cd $HOME/testFolder

cd ../ 		返回上级目录		cd ../

mv 			移动目录			mv $HOME/testFolder /var/tmp

rm -rf		删除目录			rm -rf /var/tmp/testFolder

ls			查看目录下文件/夹	ls /etc

touch		创建文件			touch ~/testFile

ls ~		查看新建文件？ 		ls ~

cp 			复制文件			cp ~/testFile ~/testNewFile

rm			输入y删除文件		rm ~/testFile

cat 		查看文件内容		cat ~/.bash\_history

grep 		过滤文件包含\*\*记录	grep 'root' /etc/passwd 	过滤出 /etc/passwd 文件中包含 root 的记录

grep -r 'linux' /var/log/		递归地过滤出 /var/log/ 目录中包含 linux 的记录

简单来说, Linux 中管道的作用是将上一个命令的输出作为下一个命令的输入, 像 pipe 一样将各个命令串联起来执行, 管道的操作符是 \|

ls /etc \| grep 'ssh'		过滤出 /etc 目录中名字包含 ssh 的目录\(不包括子目录\)

&gt;、&lt; 		重定向				可以使用 &gt; 或 &lt; 将命令的输出重定向到一个文件中		echo 'Hello World' &gt; ~/test.txt

ping		检查与其联通		ping -c 4 cloud.tencent.com 	对 cloud.tencent.com 发送 4 个 ping 包, 检查与其是否联通

netstat		查看各种网络相关信息	netstat -lt 列出所有处于监听状态的 tcp 端口

netstat -tupln	查看所有端口信息包括 PID 和进程名称

ps -aux \| grep 'ssh' 过滤得到当前系统中的 ssh 进程信息


**安装**


yum install vsftpd -y

启动服务 vsftpd

service vsftpd start



