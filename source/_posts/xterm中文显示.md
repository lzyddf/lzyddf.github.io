---
title: xterm中文显示
date: 2018-05-21 17:57:42
tags:
categories: Ubuntu
---
在家目录新建文件.Xdefaults
---
		$ sudo vi ~/.Xdefaults
	加入以下内容
		*VT100.font: 9x15
		*VT100.utf8Fonts.font: -misc-fixed-medium-r-normal--18-120-100-100-c-90-iso10646-1
	保存并退出
VNC远程登录，打开终端
---
	输入下列命令，让系统加载并生效
		# xrdb -merge ~/.Xdefaults
	回车
编辑文件的时候就可以正常显示中文啦
---
