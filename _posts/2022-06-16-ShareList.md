---
layout: post
title: ShareList快速挂载GoogleDrive、OneDrive、天翼云、蓝奏云等网盘同时挂载
tags:
- 自建网盘
image: 20.jpg
---


### 仓库地址
https://github.com/reruin/sharelist

支持部署到VPS上，支持挂载Onedrive、sharepoint；

### 如何安装-脚本安装

1.Debian/Ubuntu系统（看系统） apt-get -y install git<br>
CentOS/RHEL系统（看系统） yum -y install git <br>
下载源码 git clone https://gitee.com/Ling_N/sharelist.git <br>

国内 git clone https://github.com/reruin/sharelist.git <br>
国外 #3.执行安装 cd sharelist && bash install.sh<br>

完成后，在宝塔中安全打开 33001端口，访问 http://ip:33001，进入界面开始设置，（首次使用时将提示选在挂载源，选择挂载源，填入对应路径即可。<br> 系统内置了本地路径（FileSystem）挂载源，比如天翼云选择：账号密码挂载（Cookie方式））记住网盘文件夹要共享一下，不然会出现 500错误。

如何绑定域名-反向代理添加域名<br>
在宝塔中添加一个新站点，只绑定域名就好，完成后访问域名等待解析成功<br>
解析成功后，点网站列表右侧 设置，列表中的 反向代理，目标url设置为 <br>
http://127.0.0.1:33001，发送域名自动生成，不用操作


### 挂载本地
如果按照我的方法安装，安装路径就是：root/sharelist<br>
您可以在 sharelist文件夹内创建一个文件夹（最好为英文），然后在网站后台管理最下方，<br>
挂载源：本地文件<br>
虚拟路径：单填一个 /即挂载你整个硬盘，自己写路径<br>
注意：如果后台打开了 开放上传功能，一定要加密目录，加密方法见下面<br>

### 挂载天翼云盘
1.账号密码挂载（Cookie方式）<br>
挂载源： 189 cookic/天翼云 账号登录版<br>
挂载路径内容： <br>
填写 ，ShareList将自动开启挂载向导，按指示操作即可<br>
注意：如果填写天翼云盘的账号密码显示错误，请确保输入的是正确的，然后 Ctrl+F5强制刷新一下或者等一会就好了<br>

2.API方式挂载<br>
挂载源： 天翼云 API版<br>
挂载路径内容： <br>
填写 ，ShareList将自动开启挂载向导，按指示操作即可<br>
注意：access_token每隔30天需手动更新一次，到期前24小时内访问对应路径时会有更新提示。<br>

### 天翼企业云盘挂载
挂载源： 天翼企业云 账号密码版<br>
挂载路径内容：<br>
然后访问主页，点击挂载天翼的文件夹，会让你输入天翼云盘的账号密码，输入即可。<br>

### 挂载蓝奏云
挂载源： 蓝奏云/LanZou<br>
挂载路径内容：password@folderId<br>
password是你的链接访问密码，folderId是你的分享地址后面的bxxxxxxxx<br>
比如：分享链接：https://lanzous.com/bxxxxxxx 访问密码：xxbb<br>
挂载路径就是： xxbb@bxxxxxxxx<br>
由于蓝奏云无法上传 .jpg.mp4等格式文件，可以在后面再加个 .ct上传<br>
比如文件名为：ceshi.jpg，改为 ceshi.jpg.ct上传到蓝奏云即可<br>
注意：蓝奏云vip版可以上传大于100M的文件，但大于100M的文件无法在ShareList访问！<br>

### 挂载GoogleDrive
1.使用分享ID挂载<br>
由plugins/drive.gd.js插件实现<br>
挂载源：GDID挂载版<br>
挂载路径内容：分享的文件ID<br>

2.使用官方API挂载<br>
由plugins/drive.gd.api.js插件实现。<br>
挂载源：GD API版<br>
挂载路径内容：应用ID/root?client_secret=应用机钥&redirect_uri=回调地址&refresh_token=refresh_token/<br>
建议填写 ，ShareList将自动开启挂载向导，按指示操作即可。<br>

### 挂载OneDrive
1.使用分享ID挂载<br>
由plugins/drive.od.js插件实现<br>
挂载源：OD ID挂载版<br>
挂载路径内容：分享的文件ID<br>

2.使用官方API挂载<br>
由plugins/drive.od.api.js插件实现。<br>
挂载源：OD API版<br>
挂载路径内容：OneDrive路径->应用ID|应用机钥|回调地址|refresh_token OneDrive路径/<br>
建议填写 /，ShareList将自动开启挂载向导，按指示操作即可<br>
对于不符合OneDrive安全要求的域名，将采用中转方式验证，查看中转页面<br>
注意：由于onedrive修改了政策，个人Microsoft帐户已无法通过向导进行绑定。 需前往 Azure管理后台 注册应用并获取 app_id 和 app_secret 。<br>

3.使用官方API挂载世纪互联<br>
由plugins/drive.odc.api.js插件实现<br>
挂载源：OD 世纪互联<br>
挂载路径内容：//应用ID/路径?client_secret=应用机钥&redirect_uri=回调地址&refresh_token=refresh_token&tenant=组织名/<br>
建议填写 /，ShareList将自动开启挂载向导，按指示操作即可<br>
注意：组织名是指网盘访问链接中 https://***-my.sharepoint.cn/ 星号所示部分。<br>

4.挂载OneDrive For Business<br>
由plugins/drive.odb.js插件实现。<br>
挂载源：* OD Business 非API<br>
挂载路径内容：分享的url<br>
