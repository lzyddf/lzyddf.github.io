---
title: nodejs与npm的安装与升级
date: 2018-05-18 21:09:37
tags:
categories: Hexo
---
1、在 Github 上获取 Node.js 源码：
---
	$ sudo git clone https://github.com/nodejs/node.git
	Cloning into 'node'...
修改目录权限：
---
	$ sudo chmod -R 755 node
进入node目录
---
	$ cd node
使用 ./configure 创建编译文件
---
	$ sudo ./configure
下一步，可能时间有点长，耐心等待
---
	$ sudo make
最后
---
	$ sudo make install
查看版本
---
	$ node -v
	v0.10.25
2、安装最新版npm
---
	$ npm install npm@latest -g
