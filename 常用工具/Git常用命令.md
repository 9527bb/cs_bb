## 常用Git命令

#### 一、新建代码库
+ 在当前目录新建一个Git仓库  
	$ git init  
    
+ 新建一个目录，并将其初始化为Git代码库  
	$ git init [project-name]  
    
+ 克隆一个项目以及整个代码历史  
	$ git clone [url]
    
#### 二、Git配置
+ 显示当前的Git配置  
	$ git config --list  
    
+ 编辑Git配置文件  
	$ git config -e [--global]  
    
+ 设置提交代码时候的用户信息  
	$ git config [--global] user.name "[name]"  
   $ git config [--global] user.email "[email address]"

#### 三、增加/删除文件  
+ 添加文件到暂存区  
	$ git add [file1-name] [file2-name] ... / git add --all  
    
+ 添加指定目录到暂存区，包括子目录  
	$ git add [dir]  
    
+ 添加当前目录的所有文件到暂存区  
	$ git add .
    
+ 删除工作区文件，并且将这次删除放入暂存区  
	$ git rm [file1-name] [file2-name] ...
    
+ 修改文件名，并将这次改名放入暂存区  
	$ git mv [file-original] [file-renamed]

#### 四、代码提交
+ 提交暂存区到本地仓库  
	$ git commit -m [commit message]  
    
+ 提交暂存区的指定文件到本地仓库  
	$ git commit [file1] [file2] ... -m [message]
    
+ 提交工作区自从上次commit之后的变化，直接到本地仓库  
	$ git commit -am [message]
    
+ 提交时显示所有的diff信息  
	$ git commit -v

#### 五、分支
+ 列出本地所有分支/远程分支/所有分支  
	$ git brancn  
 	$ git branch -r  
   $ git branch -a  
   
+ 新建一个分支，但是依然停留在当前分支  
	$ git branch [branch-name]
    
+ 新建一个分支，并且切换到该分支  
	$ git checkout -b [branch-name]
    
+ 新建一个分支，并且指向指定的commit/切换到新分支  
	$ git branch [branch-name] [commit]  
   $ git checkout -b [branch-name] [commit]
   
+ 新建一个分支，并与指定的远程分支建立追踪关系/切换到新分支  
	$ git branch --track [branch-name] [remote-branch-name]  
   $ git checkout --track -b [branch-name] [remote-branch-name]
    
+ 切换到指定分支  
	$ git checkout [branch-name]
    
+ 切换到上一个使用的分支  
	$ git checkout -
    
+ 在现有分支和指定的远程分支之间建立追踪关系  
	$ git branch --set-upstream [branch-name] [remote-branch-name]  

+ 合并指定分支到当前所在分支  
	$ git merge [branch-name]
    
+ 删除分支  
	$ git branch -d [branch-name]

+ 删除远程分支  
	$ git push origin --delete [branch-name]  
   $ git branch -dr [remote/branch]

#### 六、标签
+ 列出所有tag  
	$ git tag  
    
+ 新建一个tag在当前commit  
	$ git tag [tag-name]  
 
+ 新建一个tag在指定commit  
	$ git tag [tag-name] [commit]
    
+ 删除本地tag  
	$ git tag -d [tag-name]
    
+ 删除远程tag  
	$ git push origin :refs/tags/[tag-name]
    
+ 查看tag信息
	$ git show [remote] [tag-name]
    
+ 提交指定tag  
	$ git push [remote] [tag-name]
    
+ 提交所有tag  
	$ git push [remote] --tags
    
+ 新建一个分支并指向某个tag  
	$ git checkout -b [branch-name] [tag-name]

#### 七、查看信息  
+ 显示变更的文件  
	$ git status  

+ 显示当前分支的版本历史/简化显示  
	$ git log  
   $ git log --oneline
    
+ 显示过去5次提交  
	$ git log -5 --pretty --oneline

+ 显示暂存区和工作区的差异  
 	$ git diff
 
+ 显示暂存区和上一次commit的差异  
	$ git diff --cached [file]
    
+ 显示工作区和当前分支最新的commit的差异  
	$ git diff HEAD  
 
+ 显示两次提交之间的差异  
	$ git diff [commit01] [commit02]  

+ 显示某次提交的元数据和内容的变化  
	$ git show [commit]

#### 八、远程同步
+ 下载远程仓库的所以变动  
	$ git fetch [remote]

+ 显示所有远程仓库  
	$ git remote -v

+ 显示某个远程仓库的信息  
	$ git remote show [remote]

+ 增加一个新的远程仓库，并命名  
	$ git remote add [shortname] [url]

+ 取回远程仓库的变化，并与本地同名分支合并/指定远程分支和本地分支  
	$ git pull [remote] [branch]  
   $ git pull [remote] [remote-branch]:[loacl-branch]

+ 上传本地指定分支到远程仓库同名分支/指定本地分支和远程分支  
	$ git push [remote] [branch]  
   $ git push [remote] [local-branch]:[remote-branch]

+ 强行推送当前分支到远程仓库，即使有冲突（有冲突的地方会直接使用本地进行覆盖）  
	$ git push [remote] --force

+ 推送所有分支到远程仓库  
	$ git push [remote] --all

#### 九、撤销操作  
+ 恢复暂存区的指定文件到工作区  
	$ git checkout [file]  
    
+ 恢复某个commit的指定文件到暂存区和工作区  
	$ git checkout [commit] [file]
    
+ 恢复暂存区的所有文件到工作区  
	$ git checkout .
    
+ 重置暂存区和工作区，和上次commit保持一致  
	$ git reset --hard
    
+ 重置暂存区的指定文件，与上次commit保持一致，但工作区不变  
	$ git reset [file]
    
+ 重置当前分支的指针为指定的commit，同时重置暂存区，但工作区不变  
	$ git reset [commit]
    
+ 重置当前分支的HEAD为指定的commit，同时重置暂存区和工作区，与指定的commit一致  
	$ git reset --hard [commit]
    
+ 重置当前HEAD为指定的commit，但保持暂存区和工作区不变    
	$ git reset --keep [commit]

#### 十、其他
+ 编辑操作  
	$ git rebase -i rb  

+ 合并commit记录  
	$ git rebase -i
    
#

#### 十一、个人常用
+ 日常使用  
	$ git init  
   $ git config --global user.name "glb"  
   $ git config --global user.email "xx@qq.com"  
   
   $ git clone address  
   $ git remote add shortname usrl(添加远程库)
   $ git fetch  
   $ git checkout --track -b rb origin/master  
   $ git rebase rb  
   $ git merge rb  
   
   $ git branch -d branchName  
   $ git pull origin 远程分支:本地分支  
   $ git push origin 本地分支:远程分支
   
   $ git add .  
   $ git commit -m "message"  
   $ git status  
   $ git diff(暂存区和工作区差别)  
   $ git log  
   
+ 回撤  
   $ git checkout fileName(将暂存区的文件恢复至工作区)  
   $ git checkout .(同上，全部恢复)  
   
   $ git reset fileName(重置暂存区的文件和上次commit一样，但是工作区不变)  
   $ git reset commit(重置当前分支的指针指向指定的commit，同时重置暂存区，但是工作区不变)  
   
   $ git reset --hard commit(当前分支指向指定的commit，同时工作区和暂存区重置)  
   $ git reset --keep commit(同上，但是工作区和暂存区不变)
   
    









    






























