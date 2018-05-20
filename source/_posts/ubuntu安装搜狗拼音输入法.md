---
title: ubuntu安装搜狗拼音输入法
date: 2018-05-19 11:25:49
tags:
categories: Ubuntu
---
1、下载文件
---
	进入官网http://pinyin.sogou.com/linux，下载自己对应的系统位数安装包
2、打开终端，进入下载目录
---
	$ cd Downloads/  (以实际目录为准)
3、安装
---
	$ sudo dpkg -i sougoupinyin…….deb (以你下载的实际安装包名字为标准)
4、打开Language Support
---
	如果报错，就从终端输入该命令
	$ sudo apt-get install -f 
	成功打开Language Support后，将IBus改为fcitx，然后重启电脑
5、重启后，屏幕右上角会出现键盘图标
---
	点击键盘图标，选择Configure Current Input Method
	点左下角的 +
	取消勾选Only Show Current Language
	找到sougou pinyin (一般在最底下)，点ok
6、使用ctrl+空格，切换到搜狗拼音输入法，就可以开始使用啦
---
