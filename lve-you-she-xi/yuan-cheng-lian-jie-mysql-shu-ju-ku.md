## 远程连接mysql数据库

在命令行模式下，使用

```
use mysql;
select host,user,password from user;
```

可以查看用户的状态。

#### 赋予权限

要在远端也能连接数据库，要给用户赋予权限

```
create user newuser identified by "password";
grant all on *.* to 'newuser'@'%' identified by 'password';
```

经过上面这几个步骤应该就可以了。

参考来自于[MYSQL-用户操作](http://www.cnblogs.com/zi-xing/p/4327592.html)。

