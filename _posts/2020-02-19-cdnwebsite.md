---
layout:     post
title:      "配置CDN提升博客网站的访问速度"
subtitle:   "使用 CloudFlare 提升网站访问速度"
date:       2020-02-19 19:00:00
author:     "Tickmao"
header-style: "text"
catalog:     true
tags:
    - CDN
    - 速度
    - 博客
    - GitHub Pages
    - SSL
---

本博客是部署到 GitHub Pages 上的，GitHub Pages 不仅不花钱，而且还可以使用免费的证书，可以说相当划算。但是，有个问题就是 GitHub 的服务器都部署在海外，也就是说在国内访问本博客的速度的速度会比较慢 。

之前并未觉得有什么，小小破站谁会关注呢，本来这就是自己日常写写的地方，并没有抱有多大的期望，自己可以访问就好了。

起因是近期（近几个月）Github Pages 服务的页面打开速度简直龟速，大概是网虫的脚上挂上了铅球！经常出现访问长期刷不出或等待的情况。咸鱼也是要翻身的好吗？如此压迫我的小身板。

逼逼叨着各种找（提着杀猪刀骂 niang 的样子），各种方案都有，发现比较好的一个方案是使用 CDN。好吧，啥是 CDN？你问我？我问谁啊?

好吧，我问维基百科。

## CDN

CDN，又名**内容传递网路**（英语：**C**ontent **D**elivery **N**etwork或**C**ontent **D**istribution **N**etwork，缩写：**CDN** ）是指一种透过[互联网](https://zh.wikipedia.org/wiki/互聯網)互相连接的电脑网路系统，利用最靠近每位使用者的伺服器，更快、更可靠地将音乐、图片、影片、应用程式及其他档案传送给使用者，来提供高效能、可扩展性及低成本的网路内容传递给使用者。

太官方？

其实也不官方，大致就是谁离我近我用谁。CDN 就是部署在世界各地的缓存服务器，它们会提前缓存网站上的资源，然后当用户想要访问相关资源时，直接从 CDN 服务器上取就可以了。这样不仅可以增加访问速度减少访问延迟，还可以减缓网站服务器上的压力。

## 点兵点将

世界上的 CDN 服务提供商有很多，七牛云、阿里云、腾讯云等等都提供了 CDN 服务，它们有的收费有的部分免费。

之前网站的域名解析使用的是腾讯云，所以去查了下，发现收费。你真棒，我仰望你。

又去找了下之前了解到的七牛云，说是提供每月 10GB 免费流量包，兴致满满的注册认证，发现原来七牛云的免费额度是 CDN-HTTP，也就是你的博客使用 HTTPS 协议的话是享受不到这个免费额度的。作为一个强迫症，小锁不香么？感叹号不丑么？有没有点世界和平的意识。

裤子脱了，你就给我看这个！弱弱问一句，可以取消认证么？啊，你牛，溜了溜了。

最后选择的 CDN 服务来自于 Cloudflare，这个在开源世界出现过很多次的服务商。

## CloudFlare

[Cloudflare](https://dash.cloudflare.com/) 是全球最大的 DNS 服务提供商之一。除此之外他们还提供免费的 CDN、SSL 证书等服务，并且 Cloudflare 与百度有合作，在国内也部署有大量的节点，还能顺便解决百度爬无法抓取 GitHub Pages 的问题等等。（实际就是我穷啊！要什么自行车）

### 注册登录

这个就不细讲了，网站提供了中文切换，看不懂的切换下即可。

### 配置 CDN

选择右上角的`Add site`, 添加你的域名，比如我填的是：`tickmao.com` ，不要带 http 或者 www。

![](https://ae01.alicdn.com/kf/Hf02f4a648b89425cae36e1e67e12a5deT.png)

添加好后选择免费的那个计划 ( Plan )，有钱也可以选择收费的，提供的服务更多。

![](https://ae01.alicdn.com/kf/Ha2f2c65a9af94921b09416b22f4bd432H.png)

选择之后等待读取你的 DNS 配置，一般之前 DNS 配置无误的话，只需点`Continue` 即可。之后会要求你将你的域名服务器替换为`Cloudflare `,这里也比较简单，去你的域名提供商那里管理 DNS ，移除之前的域名服务商地址，填写`Cloudflare ` 。替换成功之后，选择 `Done`。

![](https://ae01.alicdn.com/kf/H1627f844c94741ba8215147d909cfb91H.png)


等待一段时间，一般是半个小时左右。`Great news! Cloudflare is now protecting your site`, 说明设置成功。

![](https://ae01.alicdn.com/kf/Hf8365ee1a7af45598d396bffe59d0bfb2.png)


### 配置SSL

![](https://ae01.alicdn.com/kf/H227301a825d74ff08a205df8afd3ade46.png)


如果你本来的网站有 SSL 证书( Github Pages 提供)，这里会显示 Full，不需要修改 。另外将`Always Use HTTPS` 设置打开，一直使用 https 链接。

到此为之，基本设置就配置成功了。如果想知道更多，可以自行查询其他的相关设置。

## 检验

这个时候就可以打开你的站点测试一下，于我而言，发觉速度提升还是很明显的。

## 相关链接

1. [维基百科](https://zh.wikipedia.org/wiki/CDN)
2. [CloudFlare](https://www.cloudflare.com/)


**—— ChangeLog**

2020.02.19

- 博客初拟