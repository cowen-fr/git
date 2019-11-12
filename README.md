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

#### 8、暂存区和Head比对：

在向暂存区添加修改时，我们希望比对当前暂存区和Head对于版本的比对，可以使用`git diff --cached`命令。

```git
$ git diff
```

#### 9、恢复暂存区到Head版本：

当完成修改之后，使用`git add .`命令向暂存区提交修改（使用`git status`查看文件颜色由红色变为绿色）,我们可以使用`git reset HEAD`命令放弃之前的`git add .`文件操作。

```git
$ git add index.html
$ git reset HEAD
```

`git reset HEAD`命令是对所有的文件进行暂存区恢复至HEAD，如果指定特定的文件时，我们可以使用`git reset head -- demo.html`命令。

```git
$ git add .
$ git reset HEAD -- index.html
```

#### 10、恢复工作区至Head版本：

当在工作完成修改之后，并没有像暂存区执行`git add`命令，发现修改错误，我们可以使用`git checkout -- filename`命令放弃当前工作区的修改，恢复当前文件至最新的head版本。

如果放弃工作区所有文件的修改，使用`git checkout .`命令。

```git
$ git checkout -- demo.html
$ git checkout .
```

#### 11、代码的回滚：

在使用`git commit`命令提交多次文件之后，我们还可以使用`git reset --head versionno`命令使的代码回滚到某个版本，当时这种操作是很危险的，这意味着你要放弃之前的所有的提交。

```git
$ git reset --hard 914beeaec1
```

#### 12、查看不同commit之间的差异：

可以使用`git diff`命令查看不同`commit`下的版本差异化的比较，甚至可以查看不同`branch`下的文件的差异。

```git
$ git diff 4105a6d4e4c  c6f80a904e6 -- index.html
$ git diff temp master -- index.html
```

#### 13、文件的删除：

在对git管理的文件执行删除操作时，以前我们需要先删除掉文件，然后把删除信息通过`git add .`命令添加到暂存区，这样繁琐的操作可以使用`git rm ..`命令。

```git
$ git rm index.html
```

#### 14、`git stash`处理紧急任务：

对于正在进行紧急开发的开发人员，突然被安排要去处理一个紧急任务，对于这样的突发状况，我们可以使用`git stash`命令将当期的修改暂存。代码恢复到最后一次提交的状态。

- `git stash apply`：将记录恢复到`git stash`保存的状态，并且保存该`stash`信息。

- `git stash pop`：将记录恢复到`git stash`保存的状态，但是删除该`stash`信息。

#### 15、公私钥：

公私钥是`SSH`协议下上传代码的协议凭证，公私钥存放在`.ssh`文件夹下，每台计算机对应的公私钥是唯一的。

```git
$ cd ~/.ssh/   //进入ssh文件夹中
$ ls           //如果公私钥存在的话可以发现三个文件
id_rsa id_rsa.pub know_hosts
```

> Note：`id_rsa.pub`公钥存放在网上，`id_rsa`私钥存放在个人本地计算机中，公钥和私钥一一对应，才能正确的上传代码。

- 公钥的查看：

  首先进入`.ssh`文件夹下，查看所有的文件，如果公钥存在的话，会发现有对应`.pub`后缀名的文件存在。

```git
$ cd ~/.ssh/
$ ls
id_rsa id_rsa.pub
```

- 公钥的添加：

  一个电脑可以对应多个公钥，比如我们的电脑要操作多个项目，而多个项目可能会部署到多个代码托管服务器上，因此需要配置多个对应的公钥。

  公钥是和邮箱想对应的，因此不同的代码托管账户对应的邮箱也是不一样的。

```git
$ ssh-keygen -t rsa -C "example@163.com"
```

> Note：点击生成成功之后，要注意修改不同的名字，否则的话会把默认的公钥覆盖掉，造成验证失败。
