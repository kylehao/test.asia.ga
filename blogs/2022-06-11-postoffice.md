---
layout: post
title: 免费企业邮局
tags:
- 邮箱
image: 19.jpg
---


### Dingtalk.com 阿里巴巴企业邮局
http://www.Dingtalk.com

### Mail.ru 俄国企业邮局
https://biz.mail.ru/

配置方法：<br>
CNAME mail 默认 biz.mail.ru.<br>
MX @ 默认 emx.mail.ru.<br>
TXT @ 默认 mailru-domain: 2BS1wKuELHVZ86v9<br>

注：点击邮箱右下角 左后一个单词“русский” 可以修改邮箱语言<br>

### Aliyun.com 阿里免费企业邮局
http://wanwang.aliyun.com/

设置方法<br>
@MX5mxn.mxhichina.com<br>
@MX10mxw.mxhichina.com<br>
mailCNAME-mail.mxhichina.com<br>
@TXT-v=spf1 include:spf.mxhichina.com -all<br>

### Ym.163.com 3G/200账号/163邮局
http://ym.163.com


### QQ.Com 4G/200账号/免费邮局
http://domain.mail.qq.com

### 腾讯4G/200账号/免费邮局
http://exmail.qq.com<br>
https://exmail.qq.com/signupfree#signup/free

### Yandex.ru 10G/1000用户/俄国企业邮局
https://pdd.yandex.ru/domains_add/

注册方法<br>
1、yamail-c5caf92204a1 CNAME mail.yandex.ru<br>
2、MX记录 mx.yandex.net 10<br>
3、mail CNAME mail.yandex.ru<br>

目前俄语字母有33个а, б, в, г, д, е, ё, ж, з, и, й, к, л, м, н, о, п, р, с, т, у, ф, х, ц, ч, ш, щ, ъ, ы, ь, э, ю, я.<br>


### Zoho.com 5G/10用户/免费邮局/无限别名


https://www.zoho.com/mail/zohomail-pricing.html<br>
## 注册地址：
https://mail.zoho.com/orgsignup.do<br>
## 登录地址：
https://www.zoho.com/mail/login.html<br>
## 账户信息：
https://accounts.zoho.com/home#profile/personal<br>
## 管理面板：
https://mailadmin.zoho.com/cpanel/index.do<br>
## 全收邮件：
https://mailadmin.zoho.com/cpanel/home.do#domains/free163.com/settings/catchAll<br>
## 二级域名指向：
zmverify.zoho.com<br>

## 配置方法
打开：https://mail.zoho.com/cpanel/index.do?tabmode=domain#orgsettings/catchall

邮件管理--机构设置--全收邮箱，在这里添加刚才设置的管理员邮箱，即可实现无限别名。

主机名	地址	优先级<br>
@	mx.zoho.com	10<br>
@	mx2.zoho.com	20<br>
@	mx3.zoho.com	50<br>
