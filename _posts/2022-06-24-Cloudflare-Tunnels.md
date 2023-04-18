---
layout: post
title: Cloudflare-Zero Trust 免费内网穿透
tags:
- 内网穿透
image: 21.jpg
---


### Zero Trust
Zero Trust我只对tunnels有一点了解，其他的访问令牌Access什么的我用不到 就没有过多了解

tunnels就是cloudflare提供的内网穿透，,软件名字叫做”cloudflared”,windows mac linux都可用。类似与frp但是设置比frp简单一些，非常好用(但大陆因为网络环境体验感一般)

官方文档写的很详细，我将常用的功能演示一下

### Tunnels
一、内网网站映射到公网<br>
常用于家庭电脑搭建网站或中国境内封禁80 443端口的服务器做站

此内网需要可以与公网通信

前景概要：我在内网用nginx部署了三个网站 <br>
http://tunnel1.a.com <br>
http://tunnel2.a.com <br>
http://tunnel3.a.com:81<br>
我的服务器80 433端口都被封禁了，我想通过内网穿透实现通过<br>
 https://web1.smalljp.com https://web2.smalljp.com https://web3.smalljp.com 来访问它

注：

我可以部署https://tunnel1.a.com吗？

答：可以，你可以自签证书但是我不清楚cloudflared是否认可你这个证书，我个人认为没必要，因为用户端的证书是cloudflare提供的，你运行cloudflared程序的电脑和cloudflare服务器之间的内容肯定是被加密过的，所以就用http就行。另外多嘴一句 a.com 这个域名又不能被用户看到，用户看到的是web1.smalljp.com这个域名…

a.com是否有什么意义？

答：可以随便设置一个你喜欢的即使你不拥有这个域名，这个域名仅仅是用来host匹配不同server{}字段，不然都是443端口 内网机器怎么知道用户请求的哪个server，不清楚的可以了解下http协议 这方面我也不是很懂…

我机器80端口被封禁了为什么还可以将网站部署在80端口？

答：cloudflared可以访问电脑的内网80端口，然后cloudflared将数据包从任意一个未被封禁的高位端口（比如55555）将数据包发送给cloudflare服务器

正常内网穿透是用一台443端口正常的公网IP机器来作为用户与服务端的桥梁，但是cloudflare的 tunnel可以实现让cloudflare服务器作为中转机即：用户>cloudflare服务器>内网电脑的cloudflared>内网站点>cloudflared将类网站点数据通过某个端口将数据返回给cloudflare服务器>用户收到cloudflare的数据

### 步骤1：
在内网部署https://tunnel1.a.com https://tunnel2.a.com http://tunnel3.a.com:81 <br>三个网站并安装tunnels,tunnels-status显示”healthy”表示安装成功，即cloudflared可与cloudflare服务器正常通信。至此服务端配置完成，接下来在Cloudflare Zero Trust面板配置刚刚添加的tunnels-demo


### 步骤2：
在”Public Hostname”依次添加这三个隧道，

注：HTTP Setting中的HTTP Host Header一定要填写，除非你这个端口就一个内容/服务

比如我设置的nginx81端口，该端口只有一个页面，你可以不填Host这一项

你设置qbittorrent的8080端口，alist的5244端口等都是可以的

转载自： https://blog.tanglu.me/cloudflare-configure/#Tunnels