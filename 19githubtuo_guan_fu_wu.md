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
<div class="text" style=" text-align:center;">图1-15 账户配置</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-17.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-15 账户配置</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-18.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-15 账户配置</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-19.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-15 账户配置</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-20.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-15 账户配置</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-21.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-15 账户配置</div> <br/>

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-22.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-15 账户配置</div> <br/>
