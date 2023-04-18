---
layout: post
title: Office365 Onedrive无管理可以rclone webdav挂载
tags:
- 同步工具
image:  12.jpg
---


### webdav地址<br>
https://[YOUR-DOMAIN]-my.sharepoint.com/personal/[YOUR-EMAIL]/Documents

### grclone 挂载命令<br>
rclone mount webdav: /home/webdav --allow-other --vfs-cache-mode writes --allow-non-empty

### grclone 配置<br>

[sharepoint]<br>
type = webdav<br>
url = https://[YOUR-DOMAIN]-my.sharepoint.com/personal/[YOUR-EMAIL]/Documents<br>
vendor = other<br>
user = YourEmailAddress<br>
pass = encryptedpassword<br>


新增配置的时候不要选onedrive  而是选webdav  然后接下来选sharepoint 输入webdav链接（参考上面rclone官网教程）<br>
接着输入账号（就是邮箱）密码<br>
完工