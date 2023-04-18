---
layout: post
title: Migadu.com 免费邮箱转发服务
tags:
- 邮箱
image: 15.jpg
---

### 官网地址
https://www.migadu.com

### 申请地址
https://admin.migadu.com/public/signup

### 邮箱登录地址
https://webmail.migadu.com/

### 注册
注册过程也十分简单，只需要点击首页的大按钮「Start For Free」跳转到注册页面，填写你的个人邮箱和密码之后，<br>
点击「Create New Account」按钮后，前往你的个人邮箱，点击 Migadu 注册邮件中的激活链接即可完成注册。<br>
登录页面和注册页面是同一个页面，可以点击右上角的「Sign Up Free / Manage Email Domains」按钮进入，<br>
然后选择「I have an account already」就可以输入邮箱和密码进行登录操作了。<br>
登录跳转到管理页面后，也是和首页一样的简洁，没有任何多余的内容，只有必要的一些操作链接可以点击，<br>
国内的某些服务管理后台真应该学习一下呀。

### 添加域名
想要添加域名，只需要在点击「Domains → Add New Domain」后，填写你的域名，然后点击「Add Domain」进入下一步，<br>
这一步可能会需要一点时间加载，如果发现一直在加载状态，可以刷新页面后再次打开「Domains」菜单，此时应该可<br>
以看到刚刚添加的域名。<br>
在新增的域名旁边，可以看到红色的「configure」字样，表示当前域名还有配置内容没有完成。选择新添加的域名，<br>
然后打开「DNS Setup → Configuration Profile」页面，这里会需要你根据自己的 DNS 类型进行选择，一般情况下<br>
都会选择「External DNS」这一项，点击保存后会跳转到「DNS Setup → Instructions」页面，请自行根据这里的指示<br>
一步一步在你的 DNS 服务管理后台中添加相应的记录，完成之后点击「Verify DNS Configuration」会对配置信息进行<br>
验证，DNS 记录的生效需要时间，可能需要间隔一段时间之后才能完成验证步骤。<br>
在验证中的域名旁边会有一个灰色的「verifying」字样，验证通过的域名旁将不会有任何提示性的字样出现，大家可以根<br>
据这个来判断域名验证是否已经完成。

### 使用<br>
在点击域名后，可以看到前三个链接分别是 Mailboxes, Aliases 和 Catch-alls，这里对这几个常用的功能做一个简单的说明<br>

Mailboxes: <br>
这里可以创建和管理邮箱账户，每一个邮箱都可以独立使用，如接收、存储和发送邮件，也就是我们常规理解的邮箱账户<br>

Aliases: <br>
<br>这里是用来管理别名邮箱的，所谓别名邮箱简单理解就是不存在邮箱账户的邮箱地址，所有发送到别名邮箱里的邮件都会被转发到<br>
你所指定的邮箱地址中，同腾讯企业邮的「邮件转移」功能。需要注意的是，因为别名邮箱不是真实存在的邮箱，自然也就无法存储所<br>
接收到的邮件，如果希望使用别名邮箱，但是又想存储邮件内容，可以同时在 Mailboxes 和 Aliases 里创建同名的邮箱地址<br>

Catch-alls: <br>
和别名邮箱类似，在这里创建的邮箱接收到的邮件都会被转发到指定的邮箱地址中，唯一的区别是别名邮箱是一个确定的邮箱地址，<br>
而 catch-alls 里是通过正则表达式来进行邮箱地址的匹配的，也就是说只要收件地址被正则表达式命中，则会转发邮件到指定邮箱<br>