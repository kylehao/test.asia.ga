---
layout: post
title: Bluemix.net IBM提供的256M/IBM Cloud Lite/10天无开发活动自动休眠
tags:
- VPS
image:  14.jpg
---

### 申请地址
https://console.ng.bluemix.net/registration/free

### 登录地址：
https://cloud.ibm.com/login

### 可部署onemanager并用cloudflsre workers做反向代理
http://mylove520.us-south.cf.appdomain.cloud/

### 定时重启服务方案：
https://github.com/kylehao/auto_IBMWorkflow

利用Github的Actions 每周重启 IBM Cloud Fonudray<br>
下载仓库：https://github.com/wf09/IBMWorkflow<br>
创建私人仓库并生成Workflow文件，修改一下内容<br>


设置环境变量<br>
IBM_ACCOUNT：账户邮箱<br>

IBM_APP_NAME：app的名字<br>

IBM_PASSWORD：密码<br>

设置完环境变量以后记得commit一下yml文件触发Action。<br>