# 1.5.1Git提交数据

我们可以简单的把工作目录理解成是一个被Git服务程序管理的目录，Git会时刻的追踪目录内文件的改动，另外在安装好了Git服务程序后，默认就会创建好了一个叫做master的分支，我们直接可以提交数据到了
```
[root@git-node1 ~]# mkdir xubusi  #创建本地工作目录
[root@git-node1 ~]# cd xubusi/     #进入本地工作目录
[root@git-node1 xubusi]# git init  #初始为git工作目录
Initialized empty Git repository in /root/xubusi/.git/
[root@git-node1 xubusi]# touch readme  #创建文件

[root@git-node1 xubusi]# git status  #查看git状态
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#       readme.txt  #发现新建的readme.txt文件
…


[root@git-node1 xubusi]# git add readme.txt  #git添加文件至暂存区
[root@git-node1 xubusi]# git status  #再次查看状态
# Changes to be committed:
#   (use "git rm --cached <file>..." to unstage)
#       new file:   readme.txt  #发现新建立的文件readme.txt已经变绿
…

[root@git-node1 xubusi]# git commit -m "the first commit"  #git commit提交暂存取文件至git版本仓库
[master (root-commit) dde9e40] the first commit
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
 ```
