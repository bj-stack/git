# 1.3Git安装部署
Git是分布式的版本控制系统，我们只要有了一个原始Git版本仓库，就可以让其他主机克隆走这个原始版本仓库，从而使得一个Git版本仓库可以被同时分布到不同的主机之上，并且每台主机的版本库都是一样的，没有主次之分，极大的保证了数据安全性，并使得用户能够自主选择向那个Git服务器推送文件了，其实部署一个git服务器是非常简单的。

```
[root@git-node1 ~]# yum install git  #安装Git
[root@git-node1 ~]# git config --global user.name "xubusi"  #配置git使用用户
[root@git-node1 ~]# git config --global user.email "xubusi@mail.com"  #配置git使用邮箱
[root@git-node1 ~]# git config --global color.ui true

[root@git-node1 ~]# git config --list
user.name=xubusi
user.email=xubusi@mail.com
color.ui=true
```

