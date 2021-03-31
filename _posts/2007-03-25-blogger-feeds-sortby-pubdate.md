---
layout: post
title: 解决 Blogger Feed 排序问题
categories: ['text']
tags: [Blogger]

---

以前提到过 Blogger 输出 Feed 的排序问题，始终没有找到好的解决方案。最近修改了一篇旧文章，导致该文在 Feed 中被提到最新，通过 BXNA 过来的朋友对此提出了批评，愧疚的很，在网上找了找，终于算是找到了一个还算过得去的方案。阅读全文...

目前 Blogger 对 FTP 发布的 Blog 提供了一个如此格式的 Feed 地址：

	http://www2.blogger.com/feeds/blogID*/posts/default

并且仍然可以附带几个参数进行定制，针对今天这种情况，需要用到的一个就是：

	orderby=published

这样文章就不会以 Blogger 默认的 `<updated>`（修改时间）进行排序，而是按照最初的发布时间排序。

只是这样还不能解决问题，虽然排序是合适了，但是这个 `<updated>` 仍然存在，而且 Feedburner 烧录的 Feed 仍然会采用这个修改时间作为文章的发布时间。如果 Feeds 被一些聚合网站（例如 BXNA）收录，或者读者是通过 RSS 阅读器（例如 Google Reader）阅读的话，最后修改的文章仍然会被提到最前。

于是再多加一个参数 `max-results=6` 缩减 Feed 输出的条目数为6，既然排序已经是按照最初的发布时间来的，那只取最新的6条文章，这6条之前的文章即使刚刚被修改，也不会被列在 Feed 内容中。当然，只取1条最保险，但这样会对网站新用户造成不便。

至此，我使用的Feed地址为：

	http://.../posts/default?alt=rss&orderby=published&max-results=6

问题基本算是解决了，希望加了个 `alt=rss` 强制输出 RSS 2.0 格式，但是 Blogger 并没有理会，好在这个工作 Feedburner 也可完成。现在，但愿 Blogger 不会频繁变动这个 Feed 输出地址。