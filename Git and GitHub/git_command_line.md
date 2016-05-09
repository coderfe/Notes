# Git常用命令

## 创建版本库
1. 初始化仓库
	- `git init` 初始化仓库
2. 添加文件到仓库
	- `git add <file>` 添加。`git add .` 添加所有修改了的文件等待提交
	- `git commit -m <descrption>` 提交

## 版本管理
1. 查看仓库状态
	- `git status` 查看仓库的状态、文件是否被修改
	- `git diff` 查看修改的内容
2. 版本回退
	- `git reset --hard commit_id` 回退到某个（commit_id）版本
	- 回退前 `git log` 查看提交历史
	- `git log –pretty=format:"%h %s" –graph` 美化提交历史
	- 返回未来的版本前 `git reflog` 查看历史命令
3. 撤销修改
	- 做出修改未添加到暂存区时，使用`git checkout -- <file>` 丢弃工作区
	- 做出修改且添加到暂存区时，使用`git reset HEAD file` 回到上一步，然后同上一步
	- 做出修改且提交到版本库时，使用**版本回退**命令
	- `git rm <file>` 从仓库和磁盘移除文件
	- `git rm -cache <file>` Git不再进行版本控制，但保留在本地磁盘

## 远程仓库
1. 关联远程库
	- `git remote add origin git@github.com:path/reo-name.git`
	- 第一次push使用命令 `git push -u origin master`
	- 之后可使用 `git push origin master`
	- `git pull origin <branch>` 拉取远程分支并与当前本地分支合并
3. 克隆仓库
	- `git clone <url>` Git支持多种协议，`https` | `ssh`
4. 设置远程分支的url
	- `git remote set-url <name> <newName> [oldName]`

## 分支管理
1. 创建管理分支
	- 查看分支 `git branch`
	- 创建分支 `git branch <name>`
	- 切换分支 `git checkout <name>`
	- 创建+切换分支 `git checkout -b <name>`
	- 删除分支 `git branch -d <name>`
	- 强制删除分支 `git branch -D <name>`
	- 查看本地和远程的所有分支 `git branch -a`
	- 重命名分支 `git branch -m <old-name> <new-name>`
	- 删除远程分支 `git push origin --delete <name>`
2. 解决冲突
	- 手动解决冲突 `git log --graph`查看分支合并图
3. 分支管理策略
	- 合并分支 `git merge <branch>` （快速合并，没有历史记录）
	- `git merge --no--ff <branch>` 普通模式合并(可以查看历史纪录)
4. `bug` 管理
	- 修复 `bug` 时，我们会通过创建新的 `bug` 分支进行修复，然后合并，最后删除
	- 当手头工作没有完成时，先把工作现场储藏 `git stash`，然后去修复 `bug` ，修复后，再 `git stash pop` 回到工作现场
	- 查看储藏列表 `git stash --list`
	- 丢弃储藏 `git stash drop`

## 标签管理
1. 创建标签
	- 新建一个标签 `git tag` , 默认为HEAD，也可以指定一commit_id
	- `git tag -a <tagname> -m "des"` 指定标签信息
	- `git tag -s <tagname> -m "des"` PGP签名标签
	- `git tag` 查看所有的标签
2. 标签操作
	- `git push origin <tagname>` 推送一个本地标签
	- `git push origin --tags` 推送全部未推送的标签
	- `git tag -d <tagname>` 删除本地标签
	- `git push origin :refs/tags/<tagname>` 删除远程标签

## Tips
