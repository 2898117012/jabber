---
layout: post
title: Centos下Apache+Nginx+Mysql+PHP环境配置
categories: [php,apache,mysql,nginx,centos]
description: Centos下Apache+Nginx+Mysql+PHP环境配置
keywords: centos, apache,nginx,mysql,php
---

Content here

## 安装Apache

```shell
yum install -y httpd
```

### 安装Apache扩展

```shell
yum install -y httpd-manual mod_ssl mod_perl mod_auth_mysql
```

### 设置Apache端口

```shell
vi /etc/httpd/conf/httpd.conf
```

修改`Listen 80`为`Listen 8080`

### 启动Apache

```shell
service httpd start
```

### 设置开机自动启动
```shell
chkconfig httpd on
```

## 安装Nginx
### 设置Nginx安装源

> 编辑/etc/yum.repos.d/nginx.repo文件，然后把下面文件脚本添加

```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
gpgcheck=0
enabled=1
```

### 安装Nginx

```shell
yum install -y nginx
```

## 设置开机自动启动

```shell
chkconfig nginx on
```

## 启动Nginx

```shell
service nginx start
```

## 安装Mysql

```shell
yum install -y mysql mysql-server mysql-devel
```

### 启动Mysql

```shell
service mysqld start
```

### 设置开机自动启动

```shell
chkconfig mysqld on
```

## 安装PHP

```shell
yum install -y php php-mysql
```

### 安装PHP扩展

```shell
yum install -y php-mysql gd php-gd gd-devel php-xml php-common php-mbstring php-ldap php-pear php-xmlrpc php-imap
```

### 安装php-fpm

```shell
yum install -y php-fpm
```

### 设置开机自动启动

```shell
chkconfig php-fpm on 
```

### 启动php-fpm

```shell
service php-fpm start
```

### 配置Nginx的PHP环境

```shell
vim /etc/nginx/conf.d/default.conf 
```

```
//添加nginx 默认主页index.php 

location / {
	root   /usr/share/nginx/html;
	index  index.html index.htm index.php;
}

//配置nginx支持php
location ~ .php$ {
	root	html;
	fastcgi_pass	127.0.0.1:9000;
	fastcgi_index	index.php;
	fastcgi_params  SCRIPT_FILENAME  /scripts$fastcgi_script_name;
	include	fastcgi_params;
}
```

### 配置php-fpm

```shell
vim /etc/php-fpm.d/www.conf
//修改 user = apache 和 group = apache 为
user = nginx
group = nginx
```


## 开放Centos的端口

```shell
/sbin/iptables -I INPUT -p tcp --dport 80 -j ACCEPT
```

```shell
/sbin/iptables -I INPUT -p tcp --dport 8080 -j ACCEPT
```

```shell
/sbin/iptables -I INPUT -p tcp --dport 3306 -j ACCEPT
```

```shell
/etc/rc.d/init.d/iptables save
```

```shell
/etc/rc.d/init.d/iptables status
```