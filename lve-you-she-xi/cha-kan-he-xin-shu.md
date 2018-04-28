## 查看核心数

1. windows

 ``` bash
 wmic
 cpu get Name
 cpu get NumberOfCores
 cpu get NumberOfLogicalProcessors
 // VM虚拟机中的CPU选择的核心数实际是代表线程数
 ```
 参考：[CPU的核心数、线程数的关系和区别](1)

2. linux
 ``` bash
 # 查看 cpu 型号
 sudo dmidecode -s processor-version
 # 查看 cpu 个数
 grep 'physical id' /proc/cpuinfo | sort -u | wc -l
 # 查看核心数
 grep 'core id' /proc/cpuinfo | sort -u | wc -l
 # 查看线程数
 grep 'processor' /proc/cpuinfo | sort -u | wc -l
 ```
 参考：[CPU 扫盲（核心数/线程数）](2)


[1]: http://swiftlet.net/archives/2236
[2]: http://durant35.github.io/2017/05/16/hsw_CPUWipeoutIlliteracy/