---
layout: post
title: Backblaze.com 10GB/1G流量/免费B2对象云存储
tags:
- 对象存储
image:  14.jpg
---


### 登录地址<br>
https://www.backblaze.com/

### 搭配Cloudflare可无限流量


### 解析域名
1）登陆Cloudflare，添加一个域名。定义一个前缀CNAME到 f004.backblazeb2.com

2）解析完成后，浏览器打开地址 https://b2.i0lo1o.eu.org/file/ruyonet123/default.png

格式 https://域名/file/桶名称/文件名

经过一波骚操作，访问URL提示：Error 522 错误？？

### 错误原因

Cloudflare 通过纯 HTTP 而不是 HTTPS 访问上游服务器。

但是Backblaze 仅支持安全的 HTTPS 连接，因此 HTTP 请求失败。

为了解决这个问题，在 Cloudflare 仪表板的 【SSL/TLS 部分】，将加密模式从“灵活”更改为“完全（严格）”，以便 Cloudflare 通过 HTTPS 连接到 Backblaze，并且需要 CA 颁发的证书。


### 设置缓存
这个非常有必要噢~~~

B2 桶 – 自己创建的桶 – 桶设定

桶信息填写：{"cache-control":"max-age=720000"}


Cloudflare 域名仪表盘 – 规则 – 页面规则 – 创建页面规则

URL输入 上一步中设置的域名 https://b2.i0lo1o.eu.org/*

设置选择： 缓存级别 – 标准，边缘缓存TTL – 1个月


### 隐藏桶名
由于URL中暴露了桶名，CNAME的域名又很容易被猜到，怎么防止其他童鞋恶意刷你的免费额度呢？

下面介绍一下，怎么隐藏桶名~

Cloudflare 域名仪表盘 – 规则 – 转换规则- 创建转换规则 – 重写URL

传入请求匹配时：b2.i0lo1o.eu.org

路径重写到：选择 Dynamic动态，concat("/file/ruyonet123", http.request.uri.path)

这里一定要填写你自己的域名哈~~ 举一反三噢~

然后浏览器打开URL：https://b2.i0lo1o.eu.org/default.png

### API密钥
路径：My Account – 应用程序键 – 添加新的应用程序密钥

名称随意，允许访问桶 建议选择1个，其他默认即可

2）提交成功，一定要记住记住相关信息，关了以后密钥就看不到了，只能重新创建

### 文件上传，官网上传
直接登陆官网，在桶里直接上传！

### WP插件
支持Backblaze的Wordpress插件不少呢，比如下面2个！填写API密钥即可！

wordpress.org/plugins/updraftplus/

wordpress.org/plugins/ilab-media-tools/

### SDK
官方提供多种语音的SDK

https://github.com/Backblaze/

 