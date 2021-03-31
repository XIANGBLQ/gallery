---
layout: post
title: Blogger Feed 的麻烦
categories: ['text']
tags: [Blogger]
---

前不久因为 [Blogger beta](http://beta.blogger.com/) 没有发布到 Ftp 功能，打算把 blog 转换到 [Thingamablog](http://thingamablog.sourceforge.net/)（一款开源的桌面 Blog 发布软件，基于 Java），等我准备得差不多了，Blogger 却推出了这个功能，而且还支持为文章加 Label，我又把做的差不多的 Thingamablog 模板改到 Blogger 上来，之前在 Thingamablog上 写的几篇文章，放在 Blogger 上修改了一下，结果问题就出来了。Blogger 的 Feed 升级到 ATOM 1.0，而且取消了原有的 RSS 2.0 格式。在现在的 Feed 中有两个时间，一个 `<published>` ，一个 `<updated>` ，对应一个发表时间，一个修改时间。而我现在用 Feedburner 来烧制 Feed，并开启了格式转换，转换成 RSS 2.0（不转换的话，BXNA 认为原 Feed 存在格式错误）。

Feedburner 使用了那个 `<updated>`，也就是说我修改一下现有的文章，即使只改个标点，Feedburener 也会获取到这个修改时间，并把这个时间当成文章的发布时间，把文章提到最新。正是由于这个原因，我的几篇文章长时间在 [BXNA](http://blog.blueidea.com) 上位居前列，对读者造成了不便，对不起各位。

<!--more-->

这几天在网上找解决方案，也没什么收获，[找到了一些 Blogger 自带的 Feed 源地址](http://purplemoggy.blogspot.com/2006_09_01_archive.html)，放在这里存档一下。

站点文章Feed：

	http://beta.blogger.com/feeds/blogID*/posts/type*

站点评论Feed：

	http://beta.blogger.com/feeds/blogID*/comments/type*

单篇文章的评论Feed：

	http://beta.blogger.com/feeds/blogID*/postID*/comments/type*

Label Feed：

	http://beta.blogger.com/feeds/blogID*/posts/type*/-/labelname*

说明：

* blogID 和 postID 都不用说了。type 可以是 full、summary 和 default，分别对应全文、摘要和默认，默认的话根据Blogger管理后台中的设置来显示。
* 有说法是 labelname 可以有多个，中间用/隔开，但我试了一下好像不行。
* 还有两个有用的参数：`max-result` 和 `start-index` 。默认的 Feed 是从第一条开始，一共输出 25 条，如果加上 `?max-results=60` 就是输出 60 条，加上 `?start-index=5` 就是从第五条开始输出。

Update: Blogger 好像在今天不声不响的加上了 RSS Feed。