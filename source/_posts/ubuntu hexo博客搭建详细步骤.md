---
title: ubuntu hexo博客搭建详细步骤
date: 2018-05-18 20:56:36
tags:
categories: Hexo
---

安装nodejs
---
	$ sudo apt-get install nodejs

安装git
---
	$ sudo apt-get install git

Github
---
	需要有github帐号，然后在github上新建一个仓库，一定要命名为username.github.io
	进行git ssh 认证，参考https://segmentfault.com/a/1190000002645623

安装nodejs,然后使用npm安装hexo
---
	$ npm install -g hexo
	注：这时候可能会报错，需要先更新nodejs与npm版本

创建博客文件夹
---
	$ hexo init 文件夹的名字(假设为BLOG)
	进入博客文件夹
	$ cd BLOG
	$ npm install  //安装依赖

git配置
---
	$ cd BLOG
	$ git config --global user.name "username" // username为你自己的github用户名
	$ git config --global user.email "email@example.com"

关联远程仓库
---
	$ git remote add origin "仓库url"
修改配置文件 
---
	修改BLOG目录下的_config.yml里面底部的Deployment部分为
	deploy:
  	  type: git
  	  repo: git@github.com:username/username.github.io.git
  	  branch: master
