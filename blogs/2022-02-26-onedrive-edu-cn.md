---
layout: post
title: Onedrive世纪互联 5T网盘/25T SharePoint空间
tags:
- Onedrive
- 云盘
image:  24.jpg
---



### 登录地址<br>
https://portal.partner.microsoftonline.cn

## 需要特定学校的教育edu邮箱，例如东南大学、南京大学、南农、同济等和世纪互联有合作的高校

### 管理地址<br>
https://portal.azure.cn

### 获取token命令<br>
rclone authorize onedrive "客户端ID" "API密钥" --onedrive-is-21vianet-version=true

### RCLONE挂载onedrive世纪互联步骤<br>
1、选择 / Microsoft OneDrive<br>
   \ "onedrive" 前面的数字<br>
2、输入 client_id<br>
3、输入 client_secret<br>
4、选择  4 / Azure and Office 365 operated by 21Vianet in China<br>
   \ "cn"<br>
5、Edit advanced config? 选择 “NO”<br>
6、Use auto config? 选择 “NO”<br>
7、result>  使用文档最前面的命令，用windows版rclone.exe获取，粘贴到这里<br>
8、如果挂载世纪互联的onedrive ，则选择  1 / OneDrive Personal or Business<br>
   \ "onedrive"<br>
     如果挂载世纪互联的sharepoint，则选择 6 / Type in SiteID (advanced)<br>
   \ "siteid"<br>
然后使用  https://od.xkx.me/sp.php<br>
https://wakawakaee.n6.myws.ca/ 获取 SiteID 后粘贴到这里<br>
9、选择合适的目录<br>
安装完成<br>