### Git教程搞定多人开发

参考[网址](<https://mp.weixin.qq.com/s?__biz=MzU2NzczMzk5Nw==&mid=2247483753&idx=1&sn=a8d654a7f61833b976f65a9e93b4f56c&chksm=fc99faebcbee73fd8ef1b8bd777f064d90f5a8c5a628da6814065028264b174e09b1b3551176&scene=21#wechat_redirect>)

### Git命令行操作

使用Git的要领就是大量使用分支。

`git config --global user.name` 查看用户名或配置用户名

`git config --global user.email`查看email或配置email

`git clone`将远程仓库的项目克隆到本地

`git branch`查看分支

`git branch -r`查看远程分支

`git branch <name>`创建分支

`git fetch origin origin/remote_branch:your_branch`将远程分支下载到本地，并将创建分支

`git branch --set-upstream-to=origin/remote_branch your branch`将本地分支与远程分支做关联

`git pull`获取更新

`git clean -d -f`删除当前目录下没有被track过的文件和文件夹

`git merge <name>`将目标分支合并到当前分支

`git add`将内容添加到暂存区

`git commit`将添加的内容提交

`git push`将本地提交内容推送到远程仓库

`git checkout`切换分支

`git branch -d <name>`删除分支

`git stash`存储当前分支所有内容

`git stash list`查看当前分支储藏列表

`git stash apply`恢复指定储藏内容

`git stash drop`删除指定储藏内容

`git stash pop`恢复并删除指定储藏内容

`git status`显示工作目录和暂存区的状态

`git log`显示commit的详细日志

`git log —pretty=oneline`只显示commit的ID与描述

`git reset —hard HEAD`回退到最近的一个版本

`git reset —hard commit_id`根据commit_id回退到指定版本

