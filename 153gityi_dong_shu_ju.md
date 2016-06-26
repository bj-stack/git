# 1.5.3Git移动数据
```
[root@git-node1 xubusi]# git mv readme.txt test.txt  #git如果要修改文件名称,则使用git mv命令
[root@git-node1 xubusi]# git status  #查看状态发现下次提交会有一个改名操作
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#       renamed:    readme.txt -> test.txt
[root@git-node1 xubusi]# git commit -m "changed name"  #提交到git版本仓库
[master 88f3791] changed name
 2 files changed, 31 deletions(-)
 delete mode 100644 1
 rename readme.txt => test.txt (100%)

#其实可以如下方法改名
[root@git-node1 xubusi]# mv test.txt readme.txt  #先修改名称
[root@git-node1 xubusi]# git rm test.txt  #然后删除git版本仓库内的文件快照
rm 'test.txt'
[root@git-node1 xubusi]# git add readme.txt  #最后再将新的文件添加进入
[root@git-node1 xubusi]# git commit -m "changed the file name"  #提交至git版本仓库
[master 2caa209] changed the file name
 1 file changed, 0 insertions(+), 0 deletions(-)
 rename test.txt => readme.txt (100%)
 ```
