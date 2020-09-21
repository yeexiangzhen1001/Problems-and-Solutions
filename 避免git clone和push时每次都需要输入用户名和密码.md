# 避免git clone和push时每次都需要输入用户名和密码

有三种方式解决git clone时每次都需要输入用户名和密码:

## 1. **SSH免密方式**
使用git bash ssh-keygen或puttygen.exe生成公钥。


## 2. **配置全局开机存储认证信息**
下面命令会将下次弹框的账号和密码保存起来，永久使用。
```
git config --global credential.helper store
```
如果想要清除该账号和密码，使用如下命令：

```
git config --global credential.helper reset
```

想要临时存储（默认15min），使用如下命令:
```
git config --global credential.helper cache
```
windows下的临时存储命令不是上面的，应该使用下面的命令:
```
git config --global credential.helper wincred
```

## 3. **地址中携带用户信息**
在https链接里加入username:password。
```
git remote add origin https://username:password@xxx.git
```