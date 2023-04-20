
git init 初始化

git clone 克隆他人项目

git add 跟踪文件 设置缓存状态

git rm 删掉
git rm --cache 保留在目录中

git commit 提交修改

git commit -m ‘log’
git reset head～ --soft 取消本次提交

git status 查看文件状态
git diff 查看文件具体修改
git log 查看历史提交 --pretty 美化输出

git remote add orgin 链接远程仓库
git remote rename orgin origin 远程仓库名字修改

git push origin master master是分支 推送代码

git log 可以看分支
git branch --list 查看分支
git branch xxx 新建分支
git checkout xxx 切换分支

gitcommmit -am 
git checkout -b  xxx新建并且切换


git merge xxxx 合并分支

git branch -d dev 删除分支

stash 储藏功能
git stash
git stash apply 恢复
git stash list
git stash apply stash@{2}
git checkout -- test 恢复没有修改的状态
git stash pop 恢复最后一次的stars后删掉记录


git reset head～ --soft 重置reset
git reset head～ --hard 彻底毁掉之前

rebase 搬家 提交
git rebase a 把b搬到a
rebase -i 交互操作