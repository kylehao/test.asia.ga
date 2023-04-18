---
layout: post
title: Okteto.com 4核/8G内存/50G硬盘/免费搭建cloudreve教程
tags:
- 容器服务
image:  15.jpg
---

### 官网地址
https://cloud.okteto.com/

### 登录地址
使用github账号登录,支持部署Cloudreve

### 演示地址
https://cloudreve-kylehao.cloud.okteto.net/


突然发现Okteto最近支持使用Compose进行部署了，而且现在直接访问程序就可以唤醒，不需要登录控制台唤醒程序了。<br>

在Compose标签下输入以下配置即可<br>

之前分享了Okteto免费搭建Bitwarden并保留数据的方法，再来更新Cloudreve。<br>
注意事项请看上回的帖子：https://hostloc.com/thread-843155-1-1.html<br>

和Bitwarden一样，Compose栏直接输入配置即可：<br>
services:<br>
    cloudreve:<br>
        public: true<br>
        container_name: dreve<br>
        image: jialezi/cloudreve<br>
        ports:<br>
            - 5212:5212<br>
        volumes:<br>
            - /root/cloudreve<br>

