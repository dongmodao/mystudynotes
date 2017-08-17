## 查看 SHA1 和 MD5

1. 郭神《第一行代码》提到，AS 中右侧 Gradle -> 项目名 -> :app -> Tasks -> android -> signingReport。本机上尝试，未果。 

2. 使用命令行。cd 到 c:\users\yourname\.android，使用命令 ``keytool -list -keystore debug.keystore``，此时从密码是 ``android``，即可获得 SHA1 和 MD5。

3. 获取签名文件的 SHA1 指纹。在命令行中输入 `` keytool -list -v -keystore <签名文件路径>``，输入该签名文件的密码即可。