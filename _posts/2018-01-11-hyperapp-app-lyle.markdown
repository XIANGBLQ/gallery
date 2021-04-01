---
layout:     post
title:      "HyperApp利用iPhone来配置Shadowsocks"
subtitle:   "软件推荐"
date:       2018-01-11 23:50:00
author:     "Lyle"
header-img: "img/post-hyperapp.jpg"
header-mask: 0.5
catalog:     true
tags:
    - 软件
    - App
    - 产品经理
    - 博客
    - Shadowsocks
    - ss
---

# HyperApp 利用iPhone来配置Shadowsocks

2017年10月，也就是两个月前开始折腾搭建自己的博客，同时购买了自己的域名。因为博客访问速度太慢，考虑购买自己的服务器，想作为后备支持力量。同时打算给自己搭建ss，用以配和Shadowsocks客户端方便可以浏览油管工，刷一下Pinterest，顺带使用Google搜索引擎来更加精准的应对自己日常的搜索需求。

为了博客更加美观，发表博客后能够有更好的直观感受，所以考虑动手来搭建博客时，在选择方式上踟蹰不前。有同为产品行业的业界人员采用 Wordpress 来搭建博客。如[唐杰](https://tangjie.me/)或者[涨汤](http://xavieris.me/)。也有采用 Jekyll + Github Pages 的来搭建静态博客。还有 Hexo + Github Pages来搭建自己的博客。方式有很多，最终还是选择以内容创造为主，动态效果炫酷反而违背了搭建博客的初衷。至于 Hexo 还是 Jekyll ，只是当时机缘巧合看到了 [Hux](https://huangxuan.me/) 的博客，喜欢上他的这个主题，开始有了现在的博客的诞生。当然 Hexo 的 [Next](http://theme-next.iissnan.com/) 主题也很不错，我也很喜欢，但有所取舍之后还是选择了 Jekyll 。

> 所有的巧合都是别有用心。

## 购买服务器

我本意是 2.5 美元/月的，最初想开Linode的 2.5 美元/月或者 5 美元/月的套餐，可因为仅支持Paypal和信用卡，转而选择了 Vutrl 东京机房  5 美元/月，来满足自己日常上网需求，实际我用不了 1T 那么多。

对于半吊子的技术认知水平的我，如果自己去搭建环境进行配置。一步步下去成本太大，毕竟懒，总想找脚本或者相对容易的方式来解决办法，所以发现HyperApp对我而言的确是个意外惊喜。开发者整理了超过几十个常见的应用，简单而又自动化的操作方式让环境布置和管理变得非常简单。

## 添加服务器

根据相应的信息，进行填写，并保存，即可快速添加到软件列表中进行管理。

包括些主要信息：

- Name 名称：自己对服务器的备注（多服务器的时候更加实用）
- Host 主机：域名及服务器IP
- Port 端口：默认为22
- User 用户名：root权限的账号
- Password 密码：登录密码

![tianjiafuwuqi.jpg](https://i.loli.net/2018/01/12/5a579253d5265.jpg)

*HyperApp 添加服务器页面*

![fuwuqiliebiao.jpg](https://i.loli.net/2018/01/12/5a579253c5c54.jpg)

*HyperApp 服务器列表页*

填写基本信息，服务器设置成功后，即可在服务器列表中看到服务器的运行状态。

## 安装应用

通过在应用的商店进行选择应用，来搭建相应的服务，目前支持服务众多，可根据自己的需求选择合适的应用来搭建博客，设置ss等。详细设置可以参考[官方文档](https://www.hyperapp.fun/zh/)

以配置Shadowsocks账号即ss为例

![chuangjianyingyong.jpg](https://i.loli.net/2018/01/12/5a579253c5bc0.jpg)

*HyperApp 应用列表页*

![peizhiss.jpg](https://i.loli.net/2018/01/12/5a579253d5265.jpg)

*Shadowsocks信息填写页*

选择你想搭建该应用的服务器来创建一个应用。填写基本信息，创建成功后，即可在我的应用中找到对应的App。选择应用进行安装，安装成功过后即可正常使用。

当然使用需要搭配客户端，iPhone上Shadowsocks软件、wingy等均可胜任，懂的人自然懂这里就不多加阐述了。

## 小结

> 相信你一定会遇到那个你中意的“她”，就这样悄然出现你的生活里打动你，让你为其打Call，欢呼雀跃。友情也是，爱情亦是！

## 相关链接

- [HyperApp官方文档](https://www.hyperapp.fun/zh/)
- [Hux blog](https://huangxuan.me)
- [涨汤的博客](http://xavieris.me)
- [互联网产品经理@唐杰](https://tangjie.me/)
- [Hexo Theme—Next](http://theme-next.iissnan.com/)

**—— ChangeLog**

2018.01.11

- 博客初拟