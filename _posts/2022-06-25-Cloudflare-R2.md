---
layout: post
title: Cloudflare对象存储R2配置
tags:
- 对象存储
image: 25.jpg
---


### 正文：
## 1 开通R2(0元虚拟卡即可),创建存储桶，我这边取名 “tanglu“

## 2 添加域名 以下操作基于域名(域名无法自选IP),我以 r2.smalljp.com 为例

## 3 文件上传 网页端支持300MB以下的文件上传，大于300MB强烈使用rclone上传

### rclone简单教程:

rclone1.59版本以上才支持R2

Linux官方脚本：curl https://rclone.org/install.sh | sudo bash

新建rclone配置 我这里取名myr2，选择5(AWS S3那个 然后就有R2了)网上很多教程 不继续了

rclone tree myr2: #有输出桶的文件名表示配置成功

rclone copy -P /root/download myr2:/tanglu #linux命令 将该文件夹下的所有文件上传 -P参数是显示速度状态

rclone copy -P D:\qbittorrent\Download\HongKongDoll_她的秘密1 myr2:/tanglu #windows上传命令可能需要代理加速

### 以上只是基本的部分上传命令 rclone支持上传/下载/挂载等命令，详情可参考：https://sunpma.com/864.html

## 4 必须配置
配置只针对r2.smalljp.com，不影响smalljp的其他子域名

a)强制https：规则>页面规则>https://feixiang.eu.org/i/2022/12/01/m170ry.png (打开查看图片教程)

R2不支持http 未配置强制跳转https时访问未加https可能会打不开

b)缓存所有内容：规则>页面规则>https://i2.100024.xyz/2022/11/23/ixaf2d.webp

缓存可以存储到CF边缘节点 加快打开速度 大大减少B类操作

不过超过512MB的R2文件 CF 不会缓存(详见 https://developers.cloudflare.com/cache/about/default-cache-behavior)

c)不缓存大于500MB的视频 这个自己配置吧，需要知道的是大于512MB的视频需要增加一条不缓存规则 否则会出现进度条无法拖动或者视频无法播放(感谢@Oracle. 大佬的指导)，但是不影响 视频或大于512MB文件的下载，下载速度还是不限速

d)关闭自动程序攻击模式：安全性>自动程序>关闭

不关闭可能会被误判导致无法wget下载(详见 v2ex.com/t/893933 #10楼)

## 5建议配置
e)显示所有请求IP：安全性>WAF>https://i2.100024.xyz/2022/11/23/k4b0z4.webp

这样可以在”安全性>概述”看到所有访问者IP (如图 https://i2.100024.xyz/2022/11/23/k7oot0.webp)，另外推荐一下 可以将r2.smalljp.com换为”包含”主域名smalljp.com 查看所有访问者IP 并且看到哪些IP被阻挡 为什么被阻挡

f)屏蔽境外访问：安全性>WAF>https://i2.100024.xyz/2022/11/23/ka38yi.webp

这个和配置(b)一样 都是防刷B操作。如需开启规则(f) 请将(f)放在(e)前 因为匹配规则为优先匹配，我的配置:https://i2.100024.xyz/2022/11/23/kc16p6.webp

g)请求速度限制：安全性>WAF>速率限制规则 这个自己配置吧 也是为了防刷，可以参考：https://hostloc.com/thread-1094822-1-1.html

## 6杂谈
R2免费套餐：每月10G A类操作前一百万次免费 B类操作前一千万次免费(详见 https://developers.cloudflare.com/r2/platform/pricing)

R2国内速度：R2国外可以跑满 国内似乎也可以跑满？(之前做过一次统计似乎反馈还不错 https://hostloc.com/thread-1093052-1-1.html)

速度似乎不错：CF R2国内流媒体速度测试-美国VPS综合讨论-全球主机交流论坛 - Powered by Discuz! (hostloc.com)

支持对象存储的程序：alist rclone nextcloud ,还有什么我也不知道 欢迎大佬补充