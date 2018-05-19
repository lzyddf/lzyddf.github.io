---
title: ubuntu安装VMware-Tools
date: 2018-05-19 11:26:15
tags:
categories: Ubuntu
---
1、加载安装文件
---
	如果安装按钮是灰色的，右键虚拟机-设置-软盘
		使用物理驱动器：自动检测
	就可以安装了
2、拷贝
---
	加载后，VMware Tools会加载到桌面
	右键，Copy
	进入本地home/
	右键空白处，Paste
3、解压
---
	打开terminal（终端）
	输入
	tar -xzvf  VMwareTools-xxx-xxx.tar.gz（以实际为准）
	回车
4、安装
---
	进入解压后的目录
	从终端执行安装命令
	sudo ./vmware-install.pl 
	然后一直回车就可以了
