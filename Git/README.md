# Git  

定义：分布式版本控制系统  

## 安装  

1. Linux  
    `sudo apt install git # Debian/Ubuntu`  
    `sudo yum install git # RedHat`  
2. Windows  
    从[Git官网](https://git-scm.com/install/windows)直接下载安装程序，然后按默认选项安装即可。

## 配置  

1. 用户名  
     `git config --global user.name "Your Name"`    
2. 邮箱       
     `git config --global user.email "email@example.com"`

## 创建版本库  

    1. mkdir learngit  
    2. cd learngit  
    3. git init # 把当前目录变成Git可以管理的仓库，并生成.git隐藏文件，.git文件用来跟踪管理版本库  

## 文件添加到版本库  

    1. touch READ.md # 创建文件  
    2. git add READ.md # 把文件添加到仓库  
    3. git commit -m "commit instruction" # -m 输入本次提交的说明  

## 版本回退  

    1. git log #显示从最近到最远的提交日志  
    2. git reflog #查看命令历史  
    3. git reset --hard commit_id #回退到上个版本的已提交状态，--soft会回退到上个版本的未提交状态，--mixed会回退到上个版本已添加但未提交的状态  

## 工作区和暂存区  

工作区（Working Directory）：电脑中的目录  
版本库（Repository）工作区中的一个隐藏目录.git  
暂存区（Stage/index）
git add把文件添加进去，实际上就是把文件修改添加到暂存区；  
git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。  

## 管理修改  

Git跟踪并管理的是修改，而非文件。  
每次修改，如果不用git add到暂存区，那就不会加入到commit中。

## 撤销修改  

    git checkout -- readme.txt #让这个文件回到最近一次git commit或git add时的状态。  
    git reset HEAD <file>可以把暂存区的修改撤销掉（unstage），重新放回工作区：  

|       |      discard          |                   reset                               |              revert      |
|-------|-----------------------|-------------------------------------------------------|---------------------------|
|  行为  |放弃还没commit的文件更改|            把仓库强制回退到某个历史状态                  |生成反向commit，抵消某次commit|
|  场景  |     未提交            |            单人使用的分支还未提交远端仓库                |          多人协作的分支      |

## 删除文件  

    1. rm <file>  
    2. git rm <file>  
    3. git commit -m "remove test.txt"

## 远程仓库  

1. 添加远程库  
    - GitHub 创建远程库/克隆出新的仓库或者把已有本地仓库与之关联  
    - git remote add origin git@github.com:michaelliao/learngit.git  
2. 克隆远程库  
    - GitHub创建远程库
    - git clone git@github.com:michaelliao/gitskills.git  

## Git命令  

Git命令必须在Git仓库目录内执行  

|    命令     |                说明                     |
|-------------|----------------------------------------|
|  git status |          查看仓库当前的状态|
| git diff    |查看difference|

## 分支管理  

1. 创建与合并分支  
   
    查看分支：git branch
    创建分支：git branch <name>
    切换分支：git checkout <name>或者git switch <name>
    创建+切换分支：git checkout -b <name>或者git switch -c <name>
    合并某分支到当前分支：git merge <name>
    删除分支：git branch -d <name>

2. 解决冲突  

    git log --graph命令可以看到分支合并图。

3. 分支策略  

    master分支应该是非常稳定的，也就是仅用来发布新版本，平时不能在上面干活；

    那在哪干活呢？干活都在dev分支上，也就是说，dev分支是不稳定的，到某个时候，比如1.0版本发布时，再把dev分支合并到master上，在master分支发布1.0版本；

git仓库  
local respository 运行在本地的git仓库，remote respository 运行在服务器的git仓库  
GitHub 免费提供仓库的网站  
GitHub仓库分为公开仓库和私有仓库  

git init 把文件夹使用git管理起来，变成一个仓库，使用git第一步  
.git 初始化后出现，存储一切与git有关的数据，删除.git文件就取消git对文件夹的管理  

VS Code中初始化文件：File/Open Folder/左侧 Source Control/Initialize Repository  
.gitignore 声明仓库里哪些文件不受到git管理，使用：文件中写入文件名，在项目初始化时就一起创建好  

commit 提交  
dicard changes 放弃这次代码修改，把代码回退到上一次提交  
checkout(detached) 整个仓库回退到某个历史版本，只适合查看代码，左下角master回到主干（最新状态）  
commmit ID 在仓库中唯一，也叫commit Hash  



branch 分支  

Head  

WorkTree  

Git分区  
