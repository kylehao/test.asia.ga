---
layout: post
title: CloudFlare – 使用API修改CloudFlare NS记录方法
tags:
- 免费CDN
image: 19.jpg
---


### 官方文档
https://developers.cloudflare.com/api/operations/registrar-domains-update-domain


### 修改方法
进入 SHH，输入

```
curl --request PUT \
  --url https://api.cloudflare.com/client/v4/accounts/0631b4489b6555a876722bafd8806c0b/registrar/domains/yunloc.com\
  --header 'Content-Type: application/json' \
  --header 'X-Auth-Email: xxx@gmail.com' \
  --header 'X-Auth-Key: ca3a22e7988ca555827b78e1e8dfa7f22b370' \
  --data '{
  "auto_renew": true,
  "locked": false,
  "name_servers": [
    "mussel.dnspod.net",
    "crystal.dnspod.net"
  ],
  "privacy": true
}'
```


https://api.cloudflare.com/client/v4/accounts/0631b4489b6555a876722bafd8806c0b 

(域名 — 概述 — API — 账户 ID)/registrar/domains/yunloc.com （这里为要修改的域名）\

X-Auth-Email: xxx@gmail.com（登录 cloudflare 的邮箱）

X-Auth-Key: ca3a22e7988ca555827b78e1e8dfa7f22b370（我的个人资料 — API 令牌 — API 密钥 — Global API Key ）

“name_servers”: [“mussel.dnspod.net”, “crystal.dnspod.net”（修改新的 NS 地址）

结语
修改后如果想修改回 cloudflare 的 NS，反向修改即可。