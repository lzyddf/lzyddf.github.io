---
title: hexo常用命令笔记
date: 2018-05-19 09:16:39
tags:
categories: Hexo
---
进入hexo主目录文件夹（假设文件夹名为blog）
---
	$ cd blog
常用命令
---
	$ sudo hexo new post "文章名" #新建文章
	$ sudo hexo g == hexo generate #生成静态页面到public目录
	$ sudo hexo s == hexo server #开启本地预览服务
	$ sudo hexo s --debug #启动本地预览并调试
	$ sudo hexo d == hexo deploy #部署（到github仓库）
	$ sudo hexo clean #清除缓存
	$ sudo hexo generate --watch #监视文件变动
生成静态页面并部署（到github仓库）
---
	下面两个命令的作用是相同的
	$ sudo hexo g -d == hexo generate --deploy
	$ sudo hexo d -g == hexo deploy --generate
服务器
---
	$ sudo hexo server -s #静态模式
	$ sudo hexo server -p xxx #更改端口为xxx端口
	$ sudo hexo server -i xxx.xxx.xxx.xxx #自定义 IP 为 xxx.xxx.xxx.xxx
