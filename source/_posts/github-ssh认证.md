---
title: github ssh认证
date: 2018-05-19 08:18:28
tags:
categories: Hexo
---
1、设置Git的user name和email(即在github注册时填写的)
---
    	$ git config --global user.name "username"
    	$ git config --global user.email "useremail"
2、生成密钥
---
    	$ sudo ssh-keygen -t rsa -C "username or useremail"
	如果出现overwrite(y/n)，默认是n，需要在后面填写y并回车
3、添加密钥到ssh-agent
---
    	$ eval "$(ssh-agent -s)"
    	Agent pid 59566
4、拷贝ssh
---
	进入root用户的ssh目录
	$ sudo ~/.ssh
使用	$ sudo cat id_rsa.pub
或	$ sudo vim id_rsa.pub 将里面的内容复制出来
5、将拷贝出来的ssh添加ssh到github
---
	登录github，点击右上角头像-settings-SSH and GPG keys
	点击New SSH key添加，标题随意
6.测试
---
	$ sudo ssh -T git@github.com
	你将会看到：

    	The authenticity of host 'github.com (207.97.227.239)' can't be established.
    	RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
    	Are you sure you want to continue connecting (yes/no)?
	选择 yes

    	Hi XXX! You've successfully authenticated, but GitHub does not provide shell 	access.
	如果看到Hi后面是你的用户名，就说明成功了
