---
layout: post
title: 阿里云盘变身为webdav协议的文件服务器
tags:
- 自建网盘
image: 08.jpg
---


### 仓库地址
https://github.com/zxbu/webdav-aliyundriver

支持部署到VPS上，支持挂载alist并提供webdav地址；

### 如何安装-脚本安装

### Jar包运行<br>
点击下载Jar包，建议自己下载源码编译，以获得最新代码，自行编译<br>
## 编译<br>
mvn clean package -Dmaven.test.skip=true<br>
## 编译之后的文件在target文件夹，webdav*.jar<br>
cd target<br>
mv webdav*.jar webdav.jar<br>

运行<br>
java -jar webdav.jar --aliyundrive.refresh-token="your refreshToken"<br>

### 容器运行<br>
docker run -d --name=webdav-aliyundriver --restart=always -p 8080:8080  -v /etc/localtime:/etc/localtime -v /etc/aliyun-driver/:/etc/aliyun-driver/ -e TZ="Asia/Shanghai" -e <br>ALIYUNDRIVE_REFRESH_TOKEN="your refreshToken" -e ALIYUNDRIVE_AUTH_PASSWORD="admin" -e JAVA_OPTS="-Xmx1g" zx5253/webdav-aliyundriver<br>


# /etc/aliyun-driver/ 挂载卷自动维护了最新的refreshToken，建议挂载<br>
# ALIYUNDRIVE_AUTH_PASSWORD 是admin账户的密码，建议修改<br>
# JAVA_OPTS 可修改最大内存占用，比如 -e JAVA_OPTS="-Xmx512m" 表示最大内存限制为512m<br>
参数说明<br>
--aliyundrive.refresh-token<br>
    阿里云盘的refreshToken，获取方式见下文<br>
--server.port<br>
    非必填，服务器端口号，默认为8080<br>
--aliyundrive.auth.enable=true<br>
    是否开启WebDav账户验证，默认开启<br>
--aliyundrive.auth.user-name=admin<br>
    WebDav账户，默认admin<br>
--aliyundrive.auth.password=admin<br>
    WebDav密码，默认admin<br>


运行之后默认端口是8080  可以通过：8080 访问来查看文件，更可以挂载到本地，或是配合aria2和rclone自动进行下载上传操作，教程在个人签名。<br>
配合alist https://github.com/Xhofe/alist  可以直链多线程下载网盘内的文件 <br>  
风险未知 谨慎使用<br>