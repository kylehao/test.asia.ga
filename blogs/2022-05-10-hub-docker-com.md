---
layout: post
title: Hub.docker.com 免费Docker容器镜像服务/搭建无限容量不限速的网盘/可外链
tags:
- Docker镜像
image:  15.jpg
---

### 官网地址
https://hub.docker.com/


### DockerHub
1）首先需要注册一个Docker hub账号！记住账号密码后面会用到！

2）然后新建一个仓库。名称随便！

新建仓库网址：https://hub.docker.com/repository/create

在Docker Commands中复制内容（红框）


3）打开程序将上面复制的内容粘贴到仓库地址。如果没有提示输入账号密码。

请点击+ 上传一个文件，会触发输入账号密码的界面。

目前Docker Hub下载文件是CloudFlare CDN加速，所以国内速度并不理想！




### 开源项目
https://github.com/xausky/DockerRegisterCloud

本项目编写仅基于 Docker Registry HTTP API V2 未曾尝试破解或者逆向任何公司服务，用户存储的内容以及隐私性和安全性由用户自己负责以及仓库服务提供商保证，本项目未曾也没有能力负责和保证。
 

### 基本功能
命令行工具基本功能，登录，文件列表，上传文件，下载文件
直接下载，在支持的仓库服务中可以直接在浏览器中实现下载而无需客户端
命令行功能优化，重命名文件以及删除文件
GUI 客户端，预计包括 Linux, Windows, Mac OS, Android, iOS，本项目使用 Dart 编写，GUI 客户端将使用 Flutter，期待热心小伙伴的帮助。
直接下载支持到仓库可以用 Web 版客户端复制永久直链，可用于图床等
 

### 支持仓库
服务提供商	无需成本	直接下载支持
Docker Register	✖️	✖️
Docker Hub	✔️	✔️
百度智能云	✔️	✖️
阿里云	✔️	✔️
华为云	✔️	✔️
 

### 客户端
Github：https://github.com/xausky/DockerRegisterCloud/releases

国内网盘：https://lanzous.com/b0e7sv6yb

 

### 免费仓库
### 国内

阿里云：https://cr.console.aliyun.com
华为云：https://console.huaweicloud.com/swr

### 国外
Docker Hub：https://hub.docker.com/


### 准备工作
1）阿里云账号

2）本地需要下载客户端

### 操作步骤
这里主要演示利用阿里云的的免费仓库来搭建！！

### 1）开通阿里云免费的Docker存储

登陆阿里云，然后访问：https://cr.console.aliyun.com

首先要设置登陆密码！这个密码后面会使用到！

### 2）按照步骤提示注册一个命名空间！


### 3）新建仓库等！选择我们新建的命名空间！代码源选择本地仓库！

### 4）新建成功后，复制公网地址。后面我们要使用！

### 5）运行软件，仓库地址粘贴上面复制的公网地址，然后输入用户名 和密码！

特别提醒：这里的密码不是阿里云的密码，是在第一步设置的密码，请注意！

### 6）然后就可以愉快的使用啦！