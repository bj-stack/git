# 1.5.5Git还原数据
>当提交不是自己想要的，可以进行回退上一版本

```
[root@git-node1 xubusi]# echo "Git is a version control system" >> readme.txt #追加一段话
[root@git-node1 xubusi]# git add readme.txt  #添加至暂存区
[root@git-node1 xubusi]# git commit -m "introduction software" #提交至git版本仓库
[master 4bf5b29] introduction software
 1 file changed, 1 insertion(+)

此时觉得写得不妥，想还原某一次提交的文件快照
[root@git-node1 xubusi]# git log --pretty=oneline #提交的历史信息
4bf5b296db9678f1851b896ed040fe37e6d7efb5 introduction software
2caa2090efa1aaf5c32524a13c500c1524e0a5ee changed the file name
88f379175b5ead7e0d84e47bd6db6f5a3b072921 changed name
Git服务程序中有一个叫做HEAD的版本指针，当用户申请还原数据时，其实就是将HEAD指针指向到某个特定的提交版本，但是因为Git是分布式版本控制系统，为了避免历史记录冲突，故使用了SHA-1计算出十六进制的哈希字串来区分每个提交版本，另外默认的HEAD版本指针会指向到最近的一次提交版本记录，而上一个提交版本会叫HEAD^，上上一个版本则会叫做HEAD^^，当然一般会用HEAD~5来表示往上数第五个提交版本。

[root@git-node1 xubusi]# git reset --hard HEAD^  #还原历史提交版本上一次
HEAD is now at 2caa209 changed the file name
[root@git-node1 xubusi]#  cat readme.txt  #查看文件内容(已经还原)
Create new branch is linux

刚刚的操作实际上就是改变了一下HEAD版本指针的位置，就是你将HEAD指针放在那里，那么你的当前工作版本就会定位在那里，要想把内容再还原到最新提交的版本，先看查看下提交版本号
[root@git-node1 xubusi]# git log --pretty=oneline
2caa2090efa1aaf5c32524a13c500c1524e0a5ee changed the file name
88f379175b5ead7e0d84e47bd6db6f5a3b072921 changed name

怎么搞得？竟然没有了Introduction software这个提交版本记录？
原因很简单，因为我们当前的工作版本是历史的一个提交点，这个历史提交点还没有发生过Introduction software更新记录，所以当然就看不到了，要是想“还原到未来”的历史更新点，可以用git reflog命令来查看所有的历史记录：

[root@git-node1 xubusi]# git reflog  #查看未来历史更新点
2caa209 HEAD@{0}: reset: moving to HEAD^
4bf5b29 HEAD@{1}: commit: introduction software
2caa209 HEAD@{2}: commit: changed the file name

[root@git-node1 xubusi]# git reset --hard 4bf5b29  #找到历史还原点的SHA-1值后，就可以还原(值不写全,系统会自动匹配)
HEAD is now at 4bf5b29 introduction software
[root@git-node1 xubusi]# cat readme.txt  #查看文件内容(已经还原)
Create new branch is linux
Git is a version control system

如是只是想把某个文件内容还原，就不必这么麻烦，直接用git checkout命令就可以的，先写一段话
[root@git-node1 xubusi]# echo "Some mistkes words" >> readme.txt
[root@git-node1 xubusi]# cat readme.txt  #查看内容
Git is a version control system
Some mistkes words
我们突然发现不应该写一句话的,可以手工删除（当内容比较多的时候会很麻烦）,还可以将文件内容从暂存区中恢复
[root@git-node1 xubusi]# git checkout -- readme.txt
[root@git-node1 xubusi]# cat readme.txt 
Git is a version control system
这其中是有一套规则，如果暂存区中有该文件，则直接从暂存区恢复，如果暂存区没有该文件，则将还原成最近一次文件提交时的快照。
```