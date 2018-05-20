---
title: hexo备份本地目录到github
date: 2018-05-18 21:14:39
tags:
categories: Hexo
---
推送
---
	1、添加当前工作目录文件到index
		$ sudo git add .
	2、生成一个提交文件
		$ sudo git commit -a -m "commit first"
	3、推送到github的XXX分支
		$ sudo git push origin master:XXX
拉取并合并到本地
---
	1、清除git缓存
		$ sudo git clean -n
		$ sudo git clean -df
		$ sudo git clean -f
	2、拉取与合并
		$ sudo git pull origin 分支名

