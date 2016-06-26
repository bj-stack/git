# 1.9GitHub托管服务
Github顾名思义是一个Git版本库的托管服务，是目前全球最大的软件仓库，拥有上百万的开发者用户，也是软件开发和寻找资源的最佳途径，Github不仅可以托管各种Git版本仓库，还拥有了更美观的Web界面，您的代码文件可以被任何人克隆，使得开发者为开源项贡献代码变得更加容易，当然也可以付费购买私有库，这样高性价比的私有库真的是帮助到了很多团队和企业。
大多数用户都是为了寻找资源而爱上Github的，首先进入网站，点击注册(Sign up)：
<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-11.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-11 点击注册github</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-12.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-12 填写注册信息</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-13.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-13 选择仓库类型,默认免费,点击底下finish sign up注册
</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-14.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-14 GitHub账号注册完成</div> <br/>

我们在向Github推送文件时,可以选择SSH协议模式，在本机生成密钥
```
[root@git-node1 ~]# ssh-keygen  #生成密钥命令
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /root/.ssh/id_rsa.
Your public key has been saved in /root/.ssh/id_rsa.pub.
The key fingerprint is:
00:93:62:97:fd:a8:7a:7b:33:0f:2d:81:e1:11:17:b2 root@git-node1.com
The key's randomart image is:
+--[ RSA 2048]----+
|    =+o.         |
|  o +B.          |
| . oE .o         |
|   . +...        |
|    o.. S        |
|    .  o         |
|   .  o .        |
|  . . +o         |
|   ..o +.        |
+-----------------+
 [root@git-node1 ~]# cat ~/.ssh/id_rsa.pub #查看公钥
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCXv4xsa4l9fvKCDTWMvG0meoMveklG/beOvkw9xVnmFVhTg4qOCVhLXaaQtR1PJnKVhMok1vtYZu+ldAMHsSmHMuUCK2KMNFrZZaEloMeCNRkFY2vhY5XHuUBK2NjwgLjDXCYtIU40UmlFCU974ybWZJaCteIoHstLLQPoG/5PF5gqBOCeNLxkpq35jJTO9JvexeBMr2hG7NSzg9uZEDyRPUwEVY2yYZkq7hlAnR5H4f1X6HPePc64ZWLT3ZyddlK/9EXDLPu2VLMC7lj5mTGrJlQ54TU3dqSYQXzIV88GsdqxfZj8xbb9JOUZJK4KjAvqUkVmtaVFTTM77zCPUJSN root@git-node1.com
```
<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-15.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-15 账户配置</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-16.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-16 配置SSH keys</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-17.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-17 Add key添加公钥</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-18.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-18 查看ssh公钥信息</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-19.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-19 点击创建一个新的仓库</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-20.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-20 填写仓库的信息</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-21.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-21 创建成功后会跳转到该仓库,选择ssh模式,复制版本仓库克隆地址</div><br/>
```
[root@git-node1 ~]# git clone git@github.com:xubusi3/demo.git  #手动克隆测试
Cloning into 'demo'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
[root@git-node1 ~]# cat demo/README.md  #查看详细信息
# demo
描述信息--可以不写
[root@git-node1 ~]# cd demo/ #进入github clone下来的仓库
[root@git-node1 demo]# echo "test is git" >>test.txt #添加新文件
[root@git-node1 demo]# git add test.txt #添加到git暂存区
[root@git-node1 demo]# git commit -m "add test file" #提交到git版本仓库
[master 66cace0] add test file
 1 file changed, 1 insertion(+)
 create mode 100644 test.txt

[root@git-node1 demo]# git remote  #查看本机列表
origin
[root@git-node1 demo]# git push -u origin master #然后将本地的Git仓库同步到远程Github服务器上(第一次请加上参数-u，代表关联本地与远程) 
Counting objects: 4, done.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 281 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To git@github.com:xubusi3/demo.git
   1b836ba..66cace0  master -> master
Branch master set up to track remote branch master from origin.
```

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-22.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-22 刷新一下web,果然看到版本仓库已经同步了</div> <br/>