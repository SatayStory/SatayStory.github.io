---
layout: post
title:  "云服务器搭建wordpress"
date:   2019-04-08 09:00:00 +0800
categories: config
---
安装apache:

`yum install httpd httpd-devel`

启动apache:

`/etc/init.d/httpd start`

此时输入服务器的IP地址，应该看到apache的服务页面，端口不用输，apache默认就是使用80端口
 
安装mysql:

`yum install mysql mysql-server`

启动mysql:

`/etc/init.d/mysqld start`
 
安装php

`yum install php php-devel`

重启apache使php生效

`/etc/init.d/httpd restart`
 
安装php的扩展

`yum install php-mysql php-gd php-imap php-ldap php-odbc php-pear php-xml php-xmlrpc`

安装完扩展之后需要再次重启apache

`/etc/init.d/httpd restart`