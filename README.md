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

2. 配置的显示：

   显示config的配置，我们只需要加`--list`参数即可。

```git
$ git config --list --global
```

#### 2、建立git仓库：

我们在建立git仓库时，常见的场景其实只有两种：

1. 把已有的项目代码纳入git管理：

   lesson文件夹下会自动生成一个.git文件夹。

```git
$ cd lesson
$ git init
```

2. 新建的项目直接使用git管理：

   使用`git init`初始化一个lesson项目文件夹，该文件夹中会存在一个.git文件夹。

```git
$ cd project
$ git init lesson
```

#### 3、暂存区和工作区：

我们使用`git add`命令将修改防止暂存区，暂存区要向工作区提交的话使用`git commit -m `命令。

```git
$ git add index.html //将指定文件添加至暂存区
$ git add -u         //将已经纳入git管理的文件添加至暂存区，不包括新增文件
$ git add .          //将所有修改添加至暂存区，包括新增文件
```

#### 4、文件的重命名：

有的时候我们需要将相关的文件修改名称重新提交，git的操作是默认先删除文件，然后再新增一个文件。当然我们也可以使用便捷的方法：

```git
$ git mv index.html default.html
```

#### 5、查看版本历史：

使用`git log`可以查看当前的版本历史，加配不同的参数，可以实现不同的展示。

- `git log --oneline`：只展示提交的版本号和提交的message名称。

- `git log --all`：显示所有分支的版本历史。（这对于多个分支下的代码管理是很重要的）

- `git log -n4`：显示提交记录中的前4条记录。

- `git log --graph`：图形化显示版本历史。

```git
$ git log --oneline
$ git log --oneline -n4
$ git log --oneline --graph
```

#### 6、`branch`和`HEAD`：

分支可以理解为某个版本下的备份，并在该备份文件下进行的扩展。

- `git checkout -b branchname`：新建分支，并自动切换到该分支。

- `git checkout branchname`：切换分支。

- `git branch`：查看当前所有分支。

- `git branch -D branchname`：删除分支（注意删除分支时，HEAD不能指向当前要删除的分支）。

```git
$ git checkout -b demo 
$ git checkout demo
$ git branch
$ git branch -D demo
```

#### 7、修改`commit`中的提交`message`：

我们在提交代码时，会用到`git commit -m message`，但是有的时候我们感觉上次提交的message信息不完整或者不准确，可以借助`git commit --amend`进行修改。

```git
$ git commit --amend
```

> 使用`git commit --amend`命令会弹出vim编辑界面，在该界面中进行修改。


