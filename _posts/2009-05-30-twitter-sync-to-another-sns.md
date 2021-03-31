---
layout: post
title: 将 Twitter 自动同步到其他社交网站
categories: ['text']
tags: [Twitter,SNS]

---
虽然有点制造垃圾的嫌疑，但是在不同的网站上有不同的好友群，又不能强迫[海内](http://hainei.com)上的好友都去用 Twitter 或者用[校内](http://xiaonei.com)的好友都去用[饭否](http://fanfou.com)，所以能够自动把这些网站上的个人状态同步一致，倒也不是完全没有必要。

思路有很多，比如说加一个 [Hellotxt](http://hellotxt.com) 或者 [Ping.fm](http://ping.fm) 的 IM 机器人，就可以同时发布信息到 Twitter 和很多 SNS 网站上，但缺点是回复某个人的 Tweet 就很不方便。如果使用 Twitter 的桌面客户端（例如 [Tweetie](http://www.atebits.com/tweetie-mac/)），有想回复某条 Tweet 的冲动，却要到 IM 里去操作，很不爽，而且也不能使回复反链接到原始 Tweet。

所以从我个人需求出发，希望做到的是：我的操作都在 Twitter 上完成，而其他网站自动同步。经过仔细试用了一些 Twitter 网站，终于整出了这么一条曲折的道路，基本能达到要求。先看图：

将 Twitter 自动同步到 Facebook、饭否、校内、海内等网站的方法

![image](/assets/images/twitter-sync-to-sns.gif)

可以看到，这条线中一个至关重要的网站是“[嘀咕](http://digu.com/lushnis)”，这个网站的一大特点是插件多，为实现我的需求提供了很大的帮助。首先用到的是这个叫“[嘀嗒](http://digufeed.com/)”的插件，这个插件可以自动将你的 Twitter 内容同步到嘀咕网，也就是说绑定之后，每在 Twitter 上更新一条信息，嘀咕网上就会同步更新。

嘀咕网上有内容了，就用到了他的第二个插件──“[嘀神](http://www.digusync.com/)”。这个插件的用处是把你嘀咕上的信息同步更新到其他网站，支持的网站非常多，包括校内、海内、饭否、叽歪、开心网……，这样我的需求基本上就满足了。但是不幸的是，饭否在前不久封锁了嘀神的 IP，这条路到饭否的方向被截断了。

话说天无绝人之路，有一个网站支持到饭否的同步，那就是 Hellotxt，除了饭否，他支持的服务也非常多，其中就包括 Facebook。

选定 Hellotxt 之后，怎样把 Twitter 上的信息同步给他呢？其实上面用到的嘀神就号称能将信息同步到 Hellotxt，但是我尝试了一下，发需要到 Hellotxt 上申请一个 api_key，申请了几次未果，于是换了一种思路。

使用 Twitter 的朋友也许知道一个能把 RSS Feed 发布到 Twitter 的网站，叫做 [Twitterfeed](http://twitterfeed.com/)，最近他有更新，也能够将 RSS Feed 发布到 Hellotxt 了。这就解决了上面这个问题：将信息通过 RSS Feed 的方式，用 Twitterfeed 同步给 Hellotxt。（我让他去读的是嘀咕网产生的 Feed，为什么不让他直接读 Twitter 的 Feed 呢？是因为 Twitter 的 Feed 中每条信息会带有用户名加一个冒号，十分累赘。）

至此，Hellotxt 再将同步过来的信息传送到 Facebook 和饭否，我平时使用的几个服务都可以同步状态了。唯一遗憾的是 Hellotxt 得到的 Feed 信息会自动在末尾加一个 * 号，这样 Facebook 上和饭否上的信息也会带有这个 * 号，略有不雅。

最后，欢迎在 Twitter 上 Follow 我: [@lushnis](https://twitter.com/lushnis)。