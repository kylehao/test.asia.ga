---
layout: post
title: Alist通过webdav挂载世纪互联，没有API的世纪互联有救了
tags:
- 自建网盘
image: 16.jpg
---


### ALIST说明：
https://alist-doc.nn.ci/docs/driver/webdav/#onedrivesharepoint
vendor 选择Sharepoint。此功能v2.4.0之后被添加

### 世纪互联WEBDAV地址：
https://universitytongji.sharepoint.cn/teams/musicshare/Shared Documents

### 使用方法
WebDav<br>
webdav root url<br>
WebDAV根地址<br>

用户名、密码<br>

OneDrive/SharePoint<br>
选择vendor为sharepoint，支持国际版/世纪互联。<br>

对于OneDrive/SharePoint，你可以通过这个工具获取webdav根地址，如果要挂载指定的目录，在后面拼接即可。

用户名为OneDrive账号邮箱，密码即为OneDrive账号密码。

## 注意：这种方式不是直链，下载需要通过服务器中转
