---
title: ubuntu搭载网页环境
date: 2018-05-19 18:26:53
tags:
categories: Ubuntu
---
安装Apache
---
	1、安装
	$ sudo apt-get install apache2
	2、查看状态
	$ sudo service apache2 restart/status/start/stop   
	3、关闭防火墙80端口限制
	$ sudo ufw allow 80 
	后面MySQL数据库3306端口也是
	4、测试：
	访问http://Ubuntu的IP，出现It Works!网页，
安装MySQL
---
	1、安装
	$ sudo apt-get install mysql-server mysql-client
	2、测试
	$ sudo mysql -u root -p  
	3、查看状态
	$ sudo service mysql retart/status/start/stop  
	4、关闭防火墙3306端口限制
	$ sudo ufw allow 3306
安装PHP
---
	1、安装
	$ sudo apt-get install php7.0 
	$ sudo apt-get install libapache2-mod-php7.0 
	$ sudo apt-get install php7.0-mysql
	2、重启服务
	$ sudo service apache2 restart 
	$ sudo service mysql restart
	3、测试
	$ sudo vim /var/www/html/phpinfo.php
	文件中写：
	<?php echo phpinfo();?>
	4、浏览器访问：
	http:// ubuntu 地址/phpinfo.php
	出现PHP Version网页

安装phpMyAdmin
---
	1、安装
	$ sudo apt-get install phpmyadmin
	安装时：空格选择apache2，enter确定，下一步配置数据库，输入密码
	2、创建phpMyAdmin快捷方式
	$ sudo ln -s /usr/share/phpmyadmin /var/www/html  
	3、启用Apache mod_rewrite模块，后面修改wordpress链接时会用
	$ sudo a2enmod rewrite  
	4、重启服务
	$ sudo service php7.0-fpm restart 
	提示服务没找到?不去管它
	$ sudo service apache2 restart
	5、浏览器访问：http:// ubuntu 地址/phpmyadmin

配置Apache
---
	1、打开配置文件
	$ sudo vim /etc/apache2/apache2.conf
	2、添加：
	$ sudo AddType application/x-httpd-php .php .htm .html 
	$ sudo AddDefaultCharset UTF-8
	3、重启Apache服务
	$ sudo service apache2 restart
安装ufw 防火墙
---
	$ sudo apt-get install ufw
