# 1.6.2Git合并分支

现在，我们想把linux的工作成果合并到master分支上了，则可以使用”git merge”命令来将指定的的分支与当前分支合并
<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-07.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-7 git合并分之示意图
</div> <br/>
```
[root@git-node1 xubusi]# git branch  #查看是否在master分支
  linux
* master
[root@git-node1 xubusi]# git merge linux  #合并Linux分支至master
Updating 185d668..8bf5757
Fast-forward
 readme.txt | 1 +
 1 file changed, 1 insertion(+)
[root@git-node1 xubusi]# cat readme.txt  #查看合并后的readme文件
1 hehe
Create new branch is linux
[root@git-node1 xubusi]# git branch -d linux  #确认合并完成后，可以放心地删除Linux分支
Deleted branch linux (was 8bf5757).
[root@git-node1 xubusi]# git branch  #删除后，查看branch,只剩下master分支了
* master
```