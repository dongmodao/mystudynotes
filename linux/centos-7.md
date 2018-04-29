## centos 7 修改密码

 1. 重启，CTRL+ALT+DEl
 2. 快按 esc，进入弹框状态
 3. 按 e 进入设置页面
 4. 找到有 linux16 的一行，将 ``ro`` 改为 ``rw init=/sysroot/bin/sh``
 5. CTRL+X / F10 退出该模式
 6. 登入，输入 chroot
 7. 使用 passwd username 修改密码
 8. 输入 reboot，重启
 9. 新密码登录
 
 参考[Access Single User Mode (Reset Root Password)](1)
 
 [1]:https://www.vultr.com/docs/boot-into-single-user-mode-reset-root-password