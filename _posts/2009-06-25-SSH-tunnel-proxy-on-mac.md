---
layout: post
title: 在 Mac 下利用 SSH 通道翻墙
categories: ['text']

---

最近闹[护航](http://zh.wikipedia.org/zh-cn/綠壩·花季護航)又闹 GFW，昨晚 Google 一度无法访问，网上群情震怒，既然我党决定不再代表老百姓，那我们老百姓只能早作打算。谁也不愿走歪门邪道，都是被逼的！

用代理的方案很多，比如说带 Tor，或者什么门、什么界，还有一款 [Hotspot Shield](http://hotspotshield.com/) 值得推荐，跨平台，稳定易用，缺点是有广告。总的来说，作为一个生活在这个傻逼时代的傻逼环境中的有为青年，如果你还没有掌握一两种翻墙技能，个人发展将会受到很大局限。

本文的解决方案，如果你目前使用的是 MAC 系统，并拥有一个可以开 SSH 帐号的境外主机（例如 Dreamhost），则可以继续向下阅读。

#####第一步，开通 SSH 帐号

以 Dreamhost 为例，进入 Control Panel，依次进入 Users » Manage Users » Add a new user，新建一个具有 SSH 权限的帐号，如图，选第二项：SFTP: sftp (SSH ftp) file transfer access only.

![image](http://fangming.li/wimgs/blog/Dreamhost-add-ssh-user.png)


#####第二步：设置您本机的网络代理

你可以手动设置代理，但是用一个 .pac 文件会方便很多，特别是 Livid 同学已经提供了一个详细的 .pac 文件，[你可以在这里下载到](http://livid.cn/doc_view.php?doc_id=5744)。

这个文件中大部分代码都类似于这个格式：

	if (shExpMatch(url, "*.google.com/*")) { return "SOCKS 127.0.0.1:6464"; }

你可以按照这个格式添加无法正常访问的网站，注意后面那个 6464 是指定的 SOCKS 代理端口号，Livid 文件中是 7777，至于我为啥用 6464，这无关宏旨，你可以改成自己喜欢的 6969 或其他。

在网络偏好设置加载 .pac 的方法：

![image](http://fangming.li/wimgs/blog/proxy-step1.png)

![image](http://fangming.li/wimgs/blog/proxy-step2.png)
 
#####第三步：开启 SSH 通道

这步很简单，打开终端（Termial），输入这段代码：

	ssh -D 6464 yourusername@yourhost.com

其中“6464”就是上一步中提到的端口号，“yourusername”就是你刚才申请到的具有 SSH 权限的用户名，“yourhost.com”就是你的主机地址。

回车，然后会提示你输入密码，如果正确，SSH 通道就算开通了。至此，你已经可以通过 SSH 通道访问一些正常状态下无法访问的网站了。

现在的麻烦是每次想使用代理都要打开 Terminal 输入上述的命令，WOOOH 提供了一个解决方案：[创建自动重连、自动保存密码登录的SSH隧道链接](http://woooh.com/2009/03/在mac-os下创建自动重连、自动保存密码登录的ssh隧道链.html)，要用到一款叫 SSH Tunnel Manager 的软件，我之前测试过，没有成功，不知是我的人品问题还是其他。
但是昨天我在 Apple 网站上无意发现了另一个软件，解决了这个问题，看这款叫 [iSSH](http://www.apple.com/downloads/macosx/unix_open_source/issh.html) 的软件：

![image](http://fangming.li/wimgs/blog/iSSH.png)

非常简单，输入类似上述第三步的信息之后，点击“Connect”，就会打开 SSH 通道。并且你还可以点击“Just Quit”退出程序，而仍然保持 SSH 的链接。

