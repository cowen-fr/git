## Git的相关知识

#### 1、git的初始配置：

git的初始配置一般是配置用户名和电子邮件，用户名和电子邮件并不是git权限的认证，用户名和电子邮件只是用来显示仓库下用户的昵称和联系方式，并不涉及git权限的认证。

```git
$ git config --global XXXXXX
```

1. 作用域设置：

   git config的设置作用域分为`local`、`global`和`system`，默认值其实是`local`。`local`只对某个仓库有效，`global`是对当前用户所有的仓库有效，`system`是对系统所有登录的用户有效。

```git
$ git config --global user.name "cowen zheng"
$ git config --local user.name "zheng hao"
```

1. 配置的显示：

   显示config的配置，我们只需要加`--list`参数即可。

```git
$ git config --list --global
```


