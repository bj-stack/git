# 1.6.3Git分支冲突

但是Git并不能每次都为我们自动的合并分支，当遇到了内容冲突比较复杂的情况，则必须手工将差异内容处理点，比如这样的情况：
<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-08.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-8 git分支冲突示意图
</div> <br/>
```
[root@git-node1 xubusi]# git checkout -b linux  #创建分支并切换到该分支
[root@git-node1 xubusi]# git branch  #查看分支
* linux
  master
[root@git-node1 xubusi]# vim readme.txt  #编辑readme文件
[root@git-node1 xubusi]# git add readme.txt  #在Linux分支添加readme至暂存区
[root@git-node1 xubusi]# git commit -m "create two"  #在Linux分支提交readme
[linux 13a42ad] create two
 1 file changed, 1 insertion(+), 2 deletions(-)
[root@git-node1 xubusi]# git checkout master  #切换到master分支
Switched to branch 'master'
[root@git-node1 xubusi]# git branch  #查看是否切换至master分支
  linux
* master
[root@git-node1 xubusi]# vim readme.txt  #编在master分支上修改readme文件同一行的内容
[root@git-node1 xubusi]# git add readme.txt  #添加至暂存区
[root@git-node1 xubusi]# git commit -m 'create to master'  #提交至Git版本仓库
[master 75bd55c] create to master
 1 file changed, 1 insertion(+)
[root@git-node1 xubusi]# git merge linux  #合并Linux分支(冲突)
Auto-merging readme.txt
CONFLICT (content): Merge conflict in readme.txt
Automatic merge failed; fix conflicts and then commit the result.
#那么此时，我们在master与linux分支上都分别对中readme文件进行了修改并提交了，那这种情况下Git就没法再为我们自动的快速合并了，它只能告诉我们readme文件的内容有冲突，需要手工处理冲突的内容后才能继续合并
[root@git-node1 xubusi]# cat readme.txt #冲突内容如下
#Git用< <<<<<<，=======，>>>>>>>分割开了各个分支冲突的内容，我们需要手工的删除这些符号，并将内容修改
1 hehe
<<<<<<< HEAD
=======
>>>>>>> linux
Create new branch is linux
[root@git-node1 xubusi]# git add readme.txt  #再次添加至暂存区
[root@git-node1 xubusi]# git commit -m 'config'  #提交至git版本仓库
[master eb9bb83] config
[root@git-node1 xubusi]# git branch -d linux  #最后删除Linux分支结束
Deleted branch linux (was 13a42ad).
[root@git-node1 xubusi]# git branch  #检查是否删除完毕
* master
```