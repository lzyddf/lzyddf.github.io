---
title: atom编辑器的安装与使用
date: 2018-05-22 21:50:23
tags:
categories: Ubuntu
---
安装
---
	通过官网源下载最新版
		$ sudo wget https://atom.io/download/deb -O atom64.deb
		$ sudo dpkg -i atom64.deb
这时候在图形界面打开atom会报错
---
	解决办法
		$ sudo cp /usr/lib/x86_64-linux-gnu/libxcb.so.1 /usr/share/atom/
		$ cd /usr/share/atom
		$ sudo sed -i 's/BIG-REQUESTS/_IG-REQUESTS/' libxcb.so.1
