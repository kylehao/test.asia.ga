---
layout: post
title: Notion+Vercel搭建博客+cfpages绑定域名加速
tags:
- 博客
image:  07.jpg
---


### 快速开始，按照以下步骤在Vercel平台部署你的网站。<br>
### 0.Fork此Github项目：https://github.com/tangly1024/NotionNext/fork<br>
(可选) 用自己的图片替换 /public 文件夹里的 avatar.jpg、favicon.svg 和 favicon.ico<br>
在 blog.config.js 配置网站的相关信息，例如站点地址，作者信息。<br>
1.在Vercel中导入你刚fork的项目<br>

### 2. 配置你的Notion数据<br>
点击Environment Variables（环境变量），添加NOTION_PAGE_ID的值。<br>

NOTION_PAGE_ID 这个参数从何而来？<br>
(1)打开以下Notion页面，并复制到你的notion空间： (点击右上角Duplicate即可)<br>

(2)分享你的页面：点击 Share 开启 Share to web 选项<br>
<br>
(3)在页面链接中取得PAGE_ID：<br>
ctrl或cmd+L<br>
可以快速复制当前页面链接，<br>
PAGE_ID<br>
就是以下页面链接中的标红部分：<br>
https://www.notion.so/tanghh/02ab3b8678004aa69e9e415905ef32a5?v=b7eb215720224ca5827bfaa5ef82cf2d<br>

### 3.点击Deploy完成部署<br>
不到两分钟时间即可部署完成。完成后点击Go to Dashboard访问控制台，点击控制台右上角Visit按钮访问你的站点。<br>