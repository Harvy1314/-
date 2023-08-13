# git学习笔记

## git安装和配置



```
# 安装
brew install git
# 配置
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
# 初始化，版本库
$ git init

# 把git放在git仓库
# 第一步，用git add把文件添加仓库
$ git init
$ git add readme.txt
# 第二步，用git commit把文件提交到仓库，-m是提交说明
git commit -m "wrote a readme file"
commit可以一次提交很多文件
```



## 时光穿梭，看版本记录

```
# 文件修改后，看仓库记录
$ git status
# 不记得修改的话，可以使用命令查看
$ git diff     //diff=difference

# 版本回退
# 查看日志
$ git log
$ git log --pretty=oneline //输出简洁
# 回退
$ git reset --hard HEAD^//一个^代表上一个 ～100表示回退之前
# HEAD is now at e475afc add distributed//没关闭可以回退最新的 
$ git reset --hard 1094a 版本号前几位就可以
# 简而言之就是后悔药
$ git reflog 可以查看命令
```

## 工作区和暂存区

```
# 暂存区概念类似仓库，工作区类似你工作环境，每次add等于大宝你工作区的包裹
# （代码），commit就是发出快递，因此每次的发出是基于包裹是否打包
# 第一次修改 -> `git add` -> 第二次修改 -> `git commit`
# 提交的只是第一次修改的，因为第二次修改未进入暂存区
$ git diff HEAD -- readme.txt可以查看工作区和版本
# 撤销修改
$ git checkout -- file可以丢弃工作区的修改
# 注意checkout可以切换分支，因此需要加上 --
$ git checkout -- readme.txt 丢弃所有的修改
# 删除命令rm
$ git rm
# 删除后的后悔药
$ git checkout -- xxx.xx
# git checkout 版本库的版本替换工作区版本
```

## 远程仓库

```
# 第一步创建ssh-key
$ ssh-keygen -t rsa -C "youremail@example.com"
# 可以用cat命令查看ssh-key
# 第二步将ssh-key复制到github、gitee、公司项目中
# 一般来说远程库的名字是origin
# 使用git pull 拉取到本地
$ git push -u origin master
# 远程库是空，可以加上-u，将本地master和远程master分支联系
# 成功后本地提交
$ git push origin master
# 至此你有了版本库

# 删除远程库
$ git remote -v
# 根据名字删除
$ git remote rm origin

# 小结
# 关联远程库
$ git remote add origin git@server-name:path/repo-name.git
# 关联需要指定名字 例如origin
# 关联后使用推送master分支命令
$ git push -u origin master
# 每次提交后，只要有必要就可以使用命令推送最新修改
$ git push origin master

# 更简单的办法，远程网站建立一个空项目,克隆到本地
$ git clone git@github.com:michaelliao/gitskills.git
```

## 分支管理

```
# git类似一个游戏存档装置
# 创建分支，切换分支
$ git branch dev
$ git checkout dev
# 二合一，-b表示创建且切换
$ git checkout -b dev
# 查看分支
$ git branch
# 分支指向哪里，就是哪个版本
# dev分支合并到master
$ git merge dev
# 合并无报错，删除分支
$ git branch -d dev
# 查看分支
$ git branch

# 切换分支的另一个命令
$ git switch -c dev
$ git switch master

# 分支冲突
发现冲突解决后合并
$ git merge --no-ff -m "merge with no-ff" dev

# bug分支
# 临时有任务，通过储藏功能，把当前工作保存
$ git stash

# 确定bug分支，例如在master
$ git checkout master
# 创建修改bug的分支
$ git checkout -b issue-101
# 修改完成后
$ git add
$ git commit -m “”
# 完成修复切换回master分支，完成合并，删除bug分支
$ git switch master
$ git merge --no-ff -m "merged bug fix 101" issue-101

# 修改完成，返回干活
$ git switch dev
$ git status
# 两种方法
# 但是恢复后，stash内容并不删除，你需要用git stash drop来删除
$ git stash apply
# 恢复的同时把stash内容也删了
$ git stash pop
# 查看stash的list
$ git stash list
# 恢复到指定的stash
$ git stash apply stash@{0}
# bug修改也可以通过你开发中针对bug的修改，复制一份到master，等于给master放修改过程，让其修改，不过一样需要把当前保存下来

# 新功能开发
$ git switch -c feature-vulcan
$ add
$ commit
# 切回dev
git switch dev
# 合并
# 需要撤销修改，销毁修改
$ git branch -D feature-vulcan

# 多人协作
# 查看远程库
$ git remote
$ git remote -V
$ git push origin master
# 推送dev分支
$ git push origin dev
```

- `master`分支是主分支，因此要时刻与远程同步；
- `dev`分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；
- bug分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；
- feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。

```
# 同事需要开发，需要创建远程origin的dev分支到本地
$ git checkout -b dev origin/dev
# 开发过程中同步远程
$ git pull
# 当开发没有指定对应分支需要设置链接
$ git branch --set-upstream-to=origin/dev dev


# rebase 变基，把提交线捋直
#- ebase操作可以把本地未push的分叉提交历史整理成直线；
#- rebase的目的是使得我们在查看历史提交的变化时更容易，因为分叉的提交需要三#方对比。

```

1. 首先，可以试图用`git push origin <branch-name>`推送自己的修改；
2. 如果推送失败，则因为远程分支比你的本地更新，需要先用`git pull`试图合并；
3. 如果合并有冲突，则解决冲突，并在本地提交；
4. 没有冲突或者解决掉冲突后，再用`git push origin <branch-name>`推送就能成功！

如果`git pull`提示`no tracking information`，则说明本地分支和远程分支的链接关系没有创建，用命令`git branch --set-upstream-to <branch-name> origin/<branch-name>`。

这就是多人协作的工作模式，一旦熟悉了，就非常简单。

## git tag

```
# tag 起名字
$ git tag v1.0
# 查看所有标签
$ git tag 
# 忘记打标签,可以查看需要打的版本，补打
$ git log --pretty=oneline --abbrev-commit
$ git tag v0.9 f52c633
# 还可以创建带有说明的标签，用`-a`指定标签名，`-m`指定说明文字：
$ git tag -a v0.1 -m "version 0.1 released" 1094adb
$ git show v0.1

# 打错标签
# 第一种情况，仅本地
$ git tag -d v0.1
$ git push origin v1.0 //本地打的标签，推到远程
$ git push origin --tags //一次推送全部

# 第二种情况，本地，服务器
# 删除本地
$ git tag -d v0.9
# 删除远程
$ git push origin :refs/tags/v0.9
```

## git的自定义

```
# 颜色加强提示
$ git config --global color.ui true

# 忽略特殊文件
# .gitignore文件可以配置
# 示例
/*
# Windows:
Thumbs.db
ehthumbs.db
Desktop.ini

# Python:
*.py[cod]
*.so
*.egg
*.egg-info
dist
build

# My configurations:
db.ini
deploy_key_rs
*/

#自定义命令，简化使用
$ git config --global alias.st status
$ git config --global alias.co checkout
$ git config --global alias.ci commit
$ git config --global alias.br branch
$ git config --global alias.unstage 'reset HEAD'
```

甚至还有人丧心病狂地把`lg`配置成了：

```
$ git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
# 用户的Git配置文件放在用户主目录下的一个隐藏文件`.gitconfig`中：
```