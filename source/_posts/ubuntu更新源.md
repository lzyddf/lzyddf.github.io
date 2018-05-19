---
title: ubuntu更新源
date: 2018-05-18 20:10:01
tags:
categories: Ubuntu
---
1、在修改source.list前，最好先备份一份
---
	执行备份命令

	$ sudo cp /etc/apt/sources.list /etc/apt/sources.list.old
2、执行命令打开source.list文件：
---
	$ sudo vim /etc/apt/source.list

3、用新的源覆盖文件里的内容
---
	按i开启编辑模式，
	以下为清华大学源，复制进去即可

	# deb cdrom:[Ubuntu 16.04 LTS _Xenial Xerus_ - Release amd64 (20160420.1)]/ xenial main restricted
	deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial main restricted
	deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates main restricted
	deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial universe
	deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates universe
	deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial multiverse
	deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates multiverse
	deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse
	deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security main restricted
	deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security universe
	deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security multiverse
	
	按esc退出编辑模式，输入:wq保存并退出（冒号也需要输入）
4、执行更新命令
---
	$ sudo apt-get update && apt-get upgrade &&apt-get dist-upgrade
