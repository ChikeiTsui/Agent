# Git  

定义：git 分布式版本控制系统  

## 安装  

1. Linux  

    `sudo apt install git #Debian/Ubuntu`  
    `sudo yum install git #RedHat`  

2. Windows  

    从[Git官网](https://git-scm.com/install/windows)直接下载安装程序，然后按默认选项安装即可。

## 配置  

     git config --global user.name "Your Name"    
     git config --global user.email "email@example.com"

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

|       |      discard          |                   reset                               |              revert      |
|-------|-----------------------|-------------------------------------------------------|---------------------------|
|  行为  |放弃还没commit的文件更改|            把仓库强制回退到某个历史状态                  |生成反向commit，抵消某次commit|
|  场景  |     未提交            |            单人使用的分支还未提交远端仓库                |          多人协作的分支      |

branch 分支  

Head  

WorkTree  

Git分区  
