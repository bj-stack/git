# 1.6.1Git创建分支

```
[root@git-node1 xubusi]# git branch linux  #创建分支
[root@git-node1 xubusi]# git checkout linux  #切换分支
Switched to branch 'linux'
[root@git-node1 xubusi]# git branch  #查看当前分支情况,当前分支前有*号
* linux
  master
[root@git-node1 xubusi]# echo "Create new branch is linux" >> readme.txt   #我们对文件追加一行字符串
[root@git-node1 xubusi]# git add readme.txt   #提交到暂存区
[root@git-node1 xubusi]# git commit -m "new branch"  #提交到git版本仓库
[linux 8bf5757] new branch
 1 file changed, 1 insertion(+)
[root@git-node1 xubusi]# git checkout master  #我们在提交文件后再切回master分支
Switched to branch 'master'
[root@git-node1 xubusi]# cat readme.txt   #查看文件内容,发现并没有新追加的字符串
1 hehe
```