---
layout: post
title: OfficeAdmin全自动一条龙程序/90天至少访问一次各盘的前台或后台，以获取新token
tags:
- Onedrive
image: 19.jpg
---


### 仓库地址
https://github.com/qkqpttgf/OfficeAdmin

### 本程序操作过程：
1，部署到对应平台，这个操作跟OneManager一样。<br>
2，在后台添加微软帐号，当然要全局<br>
3，添加时，程序会让你登录微软帐号，授权给程序，程序自动帮你创建一个client id，自动创建一个100年的secret，自动添加3个权限<br>
4，添加好权限后，提供一个url给你，点过去后，代表组织管理员同意<br>
5，就可以正常使用了。<br>

### 权限：
Directory.ReadWrite.All<br>
RoleManagement.ReadWrite.Directory<br>
User.ReadWrite.All<br>

跟OneManager一样，可以部署在Heroku/Glitch/SCF/CFC/FC/FG上。

绑定时，登录微软帐号，授权给程序，

程序自动帮你创建一个client id，自动添加3个权限，

添加好权限后，提供一个url给你，点过去后，代表组织管理员同意,

然后回来点下一步，程序自动创建一个100年的secret，就正常使用了。

当然也可以手动输入以前创建好的。

### 功能：

搜索用户

新建/删除用户

禁止/允许用户登录

为用户分配订阅许可（直接点击许可栏）

设置/取消全局管理

重置密码（

### 需要以委托权限，所以90天至少访问一次该盘的前台或后台，以获取新token
