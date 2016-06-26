# 1.5.4Git历史记录
>**查看提交历史记录**

```
[root@git-node1 xubusi]# git log
commit 2caa2090efa1aaf5c32524a13c500c1524e0a5ee
Author: xubusi <xubusi@mail.com>
Date:   Sat Jan 16 18:32:53 2016 +0800

    changed the file name

commit 88f379175b5ead7e0d84e47bd6db6f5a3b072921
Author: xubusi <xubusi@mail.com>
Date:   Sat Jan 16 18:31:03 2016 +0800

    changed name

commit 76c486fcf5d70b6a443ba9e7dad209c6722c8bee
Author: xubusi <xubusi@mail.com>
Date:   Sat Jan 16 18:22:39 2016 +0800

    tet
```
查看最近2记录

```
[root@git-node1 xubusi]# git log -2  
commit 2caa2090efa1aaf5c32524a13c500c1524e0a5ee
Author: xubusi <xubusi@mail.com>
Date:   Sat Jan 16 18:32:53 2016 +0800

    changed the file name

commit 88f379175b5ead7e0d84e47bd6db6f5a3b072921
Author: xubusi <xubusi@mail.com>
Date:   Sat Jan 16 18:31:03 2016 +0800

    changed name
```
-p显示每次提交的内容差异,例如仅查看最近一次差异
```
[root@git-node1 xubusi]# git log -p -1
commit 2caa2090efa1aaf5c32524a13c500c1524e0a5ee
Author: xubusi <xubusi@mail.com>
Date:   Sat Jan 16 18:32:53 2016 +0800

    changed the file name

diff --git a/readme.txt b/readme.txt
new file mode 100644
index 0000000..a9b574e
--- /dev/null
+++ b/readme.txt
@@ -0,0 +1,3 @@
+1 hehe
+Create new mode two
+Create new branch is linux
diff --git a/test.txt b/test.txt
deleted file mode 100644
index a9b574e..0000000
--- a/test.txt
+++ /dev/null
@@ -1,3 +0,0 @@
-1 hehe
-Create new mode two
-Create new branch is linux
```
--stat简要显示数据增改行数，这样能够看到提交中修改过的内容，对文件添加或移动的行数，并在最后列出所有增减行的概要信息
```
[root@git-node1 xubusi]# git log --stat -2
commit 2caa2090efa1aaf5c32524a13c500c1524e0a5ee
Author: xubusi <xubusi@mail.com>
Date:   Sat Jan 16 18:32:53 2016 +0800

    changed the file name

 readme.txt | 3 +++
 test.txt   | 3 ---
 2 files changed, 3 insertions(+), 3 deletions(-)

commit 88f379175b5ead7e0d84e47bd6db6f5a3b072921
Author: xubusi <xubusi@mail.com>
Date:   Sat Jan 16 18:31:03 2016 +0800

    changed name

 1          | 31 -------------------------------
 readme.txt |  3 ---
 test.txt   |  3 +++
 3 files changed, 3 insertions(+), 34 deletions(-)
 ```
 --pretty根据不同的格式展示提交的历史信息
 ```
[root@git-node1 xubusi]# git log --pretty=oneline 
2caa2090efa1aaf5c32524a13c500c1524e0a5ee changed the file name
88f379175b5ead7e0d84e47bd6db6f5a3b072921 changed name
76c486fcf5d70b6a443ba9e7dad209c6722c8bee tet
```
以更详细的模式输出提交的历史记录
```
[root@git-node1 xubusi]# git log --pretty=fuller -2 
commit 2caa2090efa1aaf5c32524a13c500c1524e0a5ee
Author:     xubusi <xubusi@mail.com>
AuthorDate: Sat Jan 16 18:32:53 2016 +0800
Commit:     xubusi <xubusi@mail.com>
CommitDate: Sat Jan 16 18:32:53 2016 +0800

    changed the file name

commit 88f379175b5ead7e0d84e47bd6db6f5a3b072921
Author:     xubusi <xubusi@mail.com>
AuthorDate: Sat Jan 16 18:31:03 2016 +0800
Commit:     xubusi <xubusi@mail.com>
CommitDate: Sat Jan 16 18:31:03 2016 +0800

    changed name
```
还可以使用format参数来指定具体的输出格式，这样非常便于后期编程的提取分析哦，常用的格式有：

%s	提交说明。<br/>
%cd	提交日期。<br/>
%an	作者的名字。<br/>
%cn	提交者的姓名。<br/>
%ce	提交者的电子邮件。<br/>
%H	提交对象的完整SHA-1哈希字串。<br/>
%h	提交对象的简短SHA-1哈希字串。<br/>
%T	树对象的完整SHA-1哈希字串。<br/>
%t	树对象的简短SHA-1哈希字串。<br/>
%P	父对象的完整SHA-1哈希字串。<br/>
%p	父对象的简短SHA-1哈希字串。<br/>
%ad	作者的修订时间。<br/>

查看当前所有提交记录的简短SHA-1哈希字串与提交着的姓名
```
[root@git-node1 xubusi]# git log --pretty=fomat:"%h %cn" #
fomat:2caa209 xubusi
fomat:88f3791 xubusi
fomat:76c486f xubusi
```