# 1.8GitLab实践
```

1. 安装和配置必要的依赖关系Install and configure the necessary dependencies
如果你安装postfix发送邮件，请选择“网站设置”中。而不是使用后缀也可以用邮件或 配置自定义SMTP服务器。如果你想使用的进出口，请 配置为SMTP服务器。
在CentOS7，下面的命令将在系统防火墙打开HTTP和SSH访问。
yum install curl openssh-server postfix
systemctl enable sshd postfix
systemctl start sshd postfix
firewall-cmd --permanent --add-service=http
systemctl reload firewalld

2. 添加gitlab包服务器安装包Add the GitLab package server and install the package
curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash
yum install gitlab-ce

3. 配置并启动gitlab Configure and start GitLab
gitlab-ctl reconfigure
gitlab-ctl status
gitlab-ctl stop
gitlab-ctl start

4. 浏览到主机名和登录Browse to the hostname and login
Username: root 
  Password: 5iveL!fe
```