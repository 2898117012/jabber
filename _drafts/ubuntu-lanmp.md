---
layout: post
title: Ubuntu下Apache+Nginx+Mysql+PHP环境配置
categories: [php,apache,mysql,nginx,ubuntu]
description: Ubuntu下Apache+Nginx+Mysql+PHP环境配置
keywords: ubuntu, apache,nginx,mysql,php
---

Content here

## 添加源

```shell
sudo apt-get install -y language-pack-en-base
sudo LC_ALL=en_US.UTF-8 add-apt-repository ppa:ondrej/php
sudo add-apt-repository ppa:ondrej/php
```
## 更新源

```shell
sudo apt-get update
```

## 安装Apache

```shell
sudo apt-get install -y apache2
```

### 修改Apache端口

```shell
vim /etc/apache2/vim ports.conf

//修改 Listen 80 为 Listen 8080
Listen 8080
```

### 重启Apache

```shell
service apache2 restart
```

## 安装Nginx

```shell
sudo apt-get install -y nginx
```

## 安装Mysql

```shell
sudo apt-get install -y mysql-server mysql-client
```

## 安装PHP

```shell
sudo apt-get install -y php5.6
```

## 安装PHP扩展

```shell
sudo apt-get install -y php5.6-mysql php5.6-curl php5.6-gd php5.6-imagick php5.6-mcrypt php5.6-memcache php5.6-xmlrpc php5.6-xsl
```

## 安装php-fpm

```shell
sudo apt-get install -y php5.6-fpm
```

### 配置Nginx的PHP环境

```shell
vim /etc/nginx/sites-enabled/default
```

```
//添加nginx 默认主页index.php 

server{
	root   /var/www/html;
	index  index.html index.htm index.php;

	//配置nginx支持php
	location ~ .php$ {
		try_files $uri =404;
		fastcgi_pass	127.0.0.1:9000;
		fastcgi_index	index.php;
		include	fastcgi_params;
	}
}
```

### 重启Nginx

```shell
/etc/init.d/nginx restart
```

### 配置php-fpm

```shell
vim /etc/php/5.6/fpm/pool.d/www.conf
//把 listen = /var/run/php5-fpm.sock  改为
listen = 127.0.0.1:9000
```

### 重启php-fpm

```shell
/etc/init.d/php5.6-fpm restart
```