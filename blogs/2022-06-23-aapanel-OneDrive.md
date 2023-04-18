---
layout: post
title: aapanel部署微软OneDrive – 从宝塔面板移植OD插件
tags:
- aapanel
image: 24.jpg
---


用过aapanel的童鞋都知道，这个面板上没有微软OneDrive这个插件，所以这篇文章就来给aapanel部署一个微软OneDrive。

额，aapanel是宝塔面板的国际版，所以这个两个面板你都需要准备好。

### 1、aapanel
1）官网：https://www.aapanel.com

2）aapanel安装教程：https://www.daniao.org/3222.html

### 2、宝塔面板
1）我们还需要安装好宝塔面板，宝塔官网获取脚本安装即可。

2）宝塔面板安装好后，我们在软件商店安装微软OneDrive插件。

3）点击位置，找到插件位置，打包。也可以根据路径：/www/server/panel/plugin，找到msonedrive，这个文件夹打包。

4）打包后分享文件，生成外链。看图：

### 3、aapanel面板设置
1）登录你的aapanel，找到路径：/www/server/panel/plugin

2）利用远程下载把你刚刚分享的文件下载过来。

3）下载后修改下重名下，比如说为msod.tar.gz。当然这个说的有点啰嗦，直接在宝塔那边压缩好，下载，然后aapanel这里上传解压即可。

4）解压后，我们在app store里面就可以看到这个插件了，不过图标是缺失的。这里需要解决下。

### 5、微软OneDrive插件使用
看教程：宝塔面板（堡塔）微软OneDrive插件使用教程

目前宝塔的微软OneDrive插件支持od国际版和世纪互联。

### 6、备份文件测试效果
1）简单测试了下，没发现问题，可能会有问题，和在宝塔上一样可以授权成功，也能浏览目录。如果遇到问题在交流！！

