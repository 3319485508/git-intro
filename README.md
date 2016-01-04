# Git 简明指南 #

----------

## 安装 ##

[下载 git Windows 版](https://git-for-windows.github.io/)

## 创建新仓库 ##

创建新文件夹，打开，然后执行 `git init` 以创建新的 git 仓库。

## 检出仓库 ##

- 创建一个本地仓库的克隆版本：`git clone /path/to/repository`

- 如果是远端服务器上的仓库: `git clone username@host:/path/to/repository`

## 添加和提交 ##

使用如下命令添加：`git add <filename>` or `git add *`

使用如下命令提交改动：`git commit -m "代码提交信息"`

## 推送改动 ##

- 执行如下命令以将这些改动提交到远端仓库：`git push origin master` 可以把 master 换成任何分支。 

- 如果你还没有克隆现有仓库，可以使用如下命令添加：`git remote add origin <server>`

## 分支 ##

> 分支是用来将特性开发绝缘开来的。在你创建仓库的时候，master 是“默认的”分支。在其他分支上进行开发，完成后再将它们合并到主分支上。

- 创建一个叫做“feature_x”的分支，并切换过去：`git checkout -b feature_x`
- 切换回主分支：`git checkout master`
- 再把新建的分支删掉：`git branch -d feature_x`
- 除非你将分支推送到远端仓库，不然该分支就是私有的：`git push origin <branch>`

## 更新与合并 ##

- 要更新你的本地仓库至最新改动，执行：`git pull`

- 要合并其他分支到你的当前分支（例如 master），执行：`git merge <branch>`

>在这两种情况下，git 都会尝试去自动合并改动。遗憾的是，这可能并非每次都成功，并可能出现冲突（conflicts）。 这时候就需要你修改这些文件来手动合并这些冲突（conflicts）。改完之后，你需要执行如下命令以将它们标记为合并成功：`git add <filename>` 在合并改动之前，你可以使用如下命令预览差异：`git diff <source_branch> <target_branch>`

	资料来源：
	http://rogerdudler.github.io/git-guide/index.zh.html
