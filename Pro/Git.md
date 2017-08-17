# Git 笔记

```bash
git config —global user.name “fredshao"
git config —gloabl user.email “fredshao@aliyun.com"

git branch fuckdev    # 创建fuckdev分支
git checkout fuckdev  # 切换到fuckdev分支

# 将本地的origin仓库中fuckdev分支推到远程remotefuckdev分支
git push -u origin fuckdev:remotefuckdev    

# 将远程的origin仓库中remotefuckdev分支拉到本地localfuckdev分支
git pull origin remotefuckdev:localfuckdev

# 以 ssh 方式 push 本地仓库到远程
# 要添加的push 权限邮箱为 youremail@example.com
1. ssh-keygen -t rsa -C “youremail@example.com” 在.ssh 目录下生成 id_rsa id_rsa.pub
2. 登录 github，将 rsa.pub 中的内容添加到 github 的 ssh 中
3. git remote add origin git@github.com:fredshao/emacs_config.git
4. git push -u origin master

git log --pretty=oneline
git reflog
git reset --hard HEAD^      # 回到上一版本
git reset --hard 3628164    # 回到指定版本
git checkout -- file        # 丢弃工作区的修改
git reset HEAD file         # 把暂存区的修改撤销，（从暂存区拿回工作区）

总结：
1. 从工作区丢弃修改          git checkout -- file
2. 从暂存区丢弃修改(add)     git reset HEAD file
3. 从主分支丢弃修改(commit)  git reset --hard [HEAD^|665456]

#生成密钥
ssh-keygen -t rsa -C “honey@aliyun.com"

#关联远程仓库，远程库的名字就叫 origin，git 的默认叫法，也可以改成别的
git remote add origin git@github.com:honey/learngit.git

#删除关联的远程仓库
git remote remove origin

#第一次提交: 
git push -u origin master

# 以后的提交: 
git push origin master

# 克隆仓库
git clone git@github.com:honey/learngit.git

# 分支操作：
git branch											# 查看分支：
git branch <name>     		// git branch dev		# 创建分支：
git checkout <name>   		// git checkout dev		# 切换分支：
git checkout -b <name>     	// git checkout -b dev	# 创建并切换分支：
git merge <name>     		// git merge dev		# 合并某分支到当前分支：
git branch -d <name>     	// git branch -d dev	# 删除分支：

git log --graph     # 查看分支合并图
git log —graph --pretty=oneline --abbrev-commit

# 禁用 Fast forward
git merge —no-ff -m “merge with no-ff” dev

# 查看远程库信息
git remote -v

# 推送分支
git push origin master
git push origin dev

# 远程已经有分支，在本地创建并建立关联
git checkout -b dev origin/dev

# 本地已有分支和远程分支相关联
git branch - -set-upstream dev origin/dev

# 标签，相当于一个 Commit 的快照
git tag <name>
git tag -a v0.1 -m “……” # 指定标签信息
git tag v0.1 622458 	# 将一次历史提交打成 tag
git tag -d v0.1 		# 删除 tag

git push origin v0.1 	# 将一个标签推送到远程
git push origin - -tags # 将本地未推送的标签一次性推送到远程

# 删除本地分支
git tag -d v0.1

#删除远程分支
1. 先删除本地分支
2. git push origin :refs/tags/v0.1

```



