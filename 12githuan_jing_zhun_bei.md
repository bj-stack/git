# 1.2Git环境准备
以下使用`CentOS7`进行实践环境
```
[root@git-node1 ~]# cat /etc/redhat-release   #查看系统版本
CentOS Linux release 7.1.1503 (Core) 
[root@git-node1 ~]# uname -r  #查看内核版本
3.10.0-229.el7.x86_64
[root@git-node1 ~]# getenforce #确认Selinux关闭状态
Disabled
[root@git-node1 ~]# systemctl stop firewalld #关闭防火墙
[root@git-node1 ~]# ifconfig eth0|awk -F '[ ]+' 'NR==2{print $3}' #查看当前主机IP地址
192.168.56.115
```


