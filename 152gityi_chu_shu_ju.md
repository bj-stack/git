# 1.5.2Git移除数据

有些时候会向把已经添加到暂存区的文件移除，但仍然希望文件在工作目录中不丢失，换句话说，就是把文件从追踪清单中删除。
```
[root@git-node1 xubusi]# touch database  #建立文件
[root@git-node1 xubusi]# git add database   #添加文件至暂存区
[root@git-node1 xubusi]# git status  #查看当前git状态
# On branch master
# Your branch is ahead of 'origin/master' by 4 commits.
#   (use "git push" to publish your local commits)
#
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#       new file:   database
[root@git-node1 xubusi]# git rm --cached database  #将文件从git暂存区域的追踪列表移除(并不会删除当前工作目录内的数据文件)
rm 'database'
[root@git-node1 xubusi]# git status  #此时文件已经是未追踪状态了
# On branch master
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#       database
no changes added to commit (use "git add" and/or "git commit -a")
#如果想将文件数据从git暂存区和工作目录一起删除，可以做如下操作。
[root@git-node1 xubusi]# git add database  #再将database文件提交到git暂存区
[root@git-node1 xubusi]# git rm -f database  #但如果在删除之前数据文件已经被放入到暂存区域的话，git会担心你误删未提交的文件而报错信息，此时可追加强制删除-f参数。
rm 'database'
[root@git-node1 xubusi]# ls  #查看工作区也没database文件
LICENSE  deploy  help.md  readme.txt
[root@git-node1 xubusi]# git status  #查看当前状态
# On branch master
no changes added to commit (use "git add" and/or "git commit -a")
```
