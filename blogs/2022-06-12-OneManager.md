---
layout: post
title: OneManager-php Onedrive目录直读程序
tags:
- 自建网盘
image: 16.jpg
---


### 仓库地址
https://github.com/qkqpttgf/OneManager-php

支持部署到虚拟主机、VPS、SERVERLESS、容器服务等，支持挂载Onedrive、sharepoint和支持挂载Onedrive分享链接

### VPS部署，配置伪静态规则
Apache伪静态规则<br>
RewriteEngine On<br>
RewriteRule ^(.*) index.php?/$1 [L]<br>

Nginx伪静态规则<br>
rewrite ^/(.*) /index.php?/$1 last;<br>


### Vercel部署目录直读程序
注意：<br>
1，Vercel的环境变量修改后不会生效，要重新部署一次才生效，所以每次修改配置，程序会部署一下，部署时间20-40s左右，请等待。<br>
2，Vercel每天API操作免费次数为100次（不是测试程序应该不会达到）。<br>
3，Vercel的环境变量限制为4K，跟SCF一样，这样最多添加3个OD。<br>
4，Vercel会被墙或被地区运营商污染。<br>

项目地址： https://github.com/qkqpttgf/OneManager-php  <br>
部署方法：在readme里有，下载代码后解压，通过token上传部署。<br>

另外： https://hostloc.com/thread-878285-1-1.html 中说Glitch给的默认域名不能改，是可以改的。<br>

最后：https://onemanager.vercel.app/  这个是哪位用啦，能让我用用吗，求求你啦。<br>


部署方法：<br>
1. Download zip from https://github.com/qkqpttgf/OneManager-php<br>
2. Unzip it, select the folder at below:  https://scfonedrive.github.io/Vercel/Deploy.html<br>

3. Click here to Creat a token, and input:<br>
Token: <br>
4. Input the name for your project:<br>
Name: <br>
onemanager<br>

you can overlay an existed project<br>
5. Click the deploy button<br>

### Cloudflare workers kv 版本，功能还不完善
https://github.com/qkqpttgf/OneManager-cfworkerskv


### 部署到 Replit
官网<br>
https://repl.it/<br>
https://replit.com/<br>

注意<br>
直接Import from Github通过.replit文件指定php时，网页会空白，有人帮忙解决吗？<br>

安装<br>
点右上的 "+" 或左上的 "+ Create Repl"，template中输入php，点选"PHP Web Server"，在"Title"里输入你想要的名称或者让它默认, 点下面的"+ Create Repl"。<br>
结束后，在右边的Console或Shell里输入 <br>
git clone https://github.com/qkqpttgf/OneManager-php && mv -b OneManager-php/* ./ && mv -b OneManager-php/.[^.]* ./ && rm -rf *~ && rm -rf OneManager-php<br>
敲回车运行。<br>
点上方的绿色 "Run" 按钮，右边会显示一个网页，你要在新窗口打开它来安装，不然不能登录。<br>

### 部署到 Glitch
官网<br>
https://glitch.com/

Demo<br>
https://onemanager.glitch.me/

安装<br>
点 [New Project] -> 点 [Import form Github] -> 粘贴 "https://github.com/qkqpttgf/OneManager-php" ，结束后，左上角点 [Show] -> [In a New Window]。

