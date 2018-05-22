---
title: ubuntu服务器开启图形界面
date: 2018-05-21 17:55:39
tags:
categories: Ubuntu
---
开启图形界面
---
	1、获取root用户权限
		$ sudo su root
	2、更新系统软件列表与软件包
		# apt-get update
		# apt-get upgrade
	3、安装gnome核心组件
		# apt-get install --no-install-recommends ubuntu-desktop gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal -y
	4、安装VNC
		# apt-get install vnc4server
	5、配置VNC
		输入下面命令，启动VNC,并让它生成一个配置文件。
		这里会让你输入一个 连接密码，请记住这个密码。
			# vncserver :1
		然后输入下面命令，以VNC关闭进程。防止因为文件被占用而修改配置文件时报错。
			# vncserver -kill :1
		然后输入下面命令，以打开VNC启动配置文件。
			# vi ~/.vnc/xstartup
		在 "x-window-manager &" 前面添加一个"#"，以注释不再需要的配置。
		然后在文件最后加入一段配置信息
			gnome-panel &
			gnome-settings-daemon &
			metacity &
			nautilus &
		保存并退出（按两次ESC退出编辑模式，输入":wq"，回车）
	6、防火墙配置
		打开服务器控制台的防火墙，添加规则
			自定义-TCP-5901
		重启服务器
VNC配置
---
	1、服务器上的配置
		先获取root用户权限
			$ sudo su root
		启动vnc服务
			# vncserver :1
		回车
	2、在本地安装VNC客户端
		官网：https://www.realvnc.com/en/connect/download/viewer/
	3、客户端配置
		安装好后，在客户端安装目录找到vncviewer，双击打开
		在客户端界面的文本框输入"公网IP:1"（引号不用，公网IP就是服务器的IP地址）
		输入在服务器配置VNC时设置的密码，OK，就能连接到图形界面了
解决中文乱码问题
---
	1、获取root用户权限
		$ sudo su root
	2、在终端依次输入下列命令
		# aptitude install font-manager
		# aptitude install ttf-arphic-uming
		# aptitude install ttf-arphic-ukai
		# aptitude install ttf-wqy-zenhei xfonts-wqy ttf-wqy-microhei
		# aptitude install fonts-cwtex-fs
		# aptitude install ttf-hanazono
		# apt-get install ttf-mscorefonts-installer
		# mkfontscale
		# mkfontdir
		# fc-cache -fv
	3、重启VNC服务，即可正常显示中文
