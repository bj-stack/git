# 1.7Git标签管理

当版本仓库内的数据有个大的改善或者功能更新，我们经常会打一个类似于软件版本号的标签，这样通过标签就可以将版本库中的某个历史版本给记录下来，方便我们随时将特定历史时期的数据取出来用，另外打标签其实只是像某个历史版本做了一个指针，所以一般都是瞬间完成的。
```
[root@git-node1 ~]# cd xubusi/  #进入git版本控制系统
[root@git-node1 xubusi]# git tag v1.0  #当前提交内容打一个标签(方便快速回滚)
[root@git-node1 xubusi]# git tag #查看当前所有的标签
v1.0
[root@git-node1 xubusi]# git show v1.0  #查看当前1.0版本的详细信息
commit 4bf5b296db9678f1851b896ed040fe37e6d7efb5
Author: xubusi <xubusi@mail.com>
Date:   Sat Jan 16 19:02:14 2016 +0800

    introduction software

diff --git a/readme.txt b/readme.txt
index a9b574e..412b267 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,3 +1,4 @@
 1 hehe
 Create new mode two
 Create new branch is linux
+Git is a version control system
[root@git-node1 xubusi]# git tag v1.2 -m "version 1.2 release is test" #创建带有说明的标签,-a指定标签名字，-m指定说明文字
[root@git-node1 xubusi]# git tag -d v1.0 #我们为同一个提交版本设置了两次标签,删除之前的v1.0
Deleted tag 'v1.0' (was 4bf5b29)
[root@git-node1 xubusi]# git tag  #再次查看,v1.0已经被删除
v1.2
```