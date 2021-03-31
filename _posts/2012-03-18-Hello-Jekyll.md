---
layout: post
categories: ['text']
---

Blog 系统换为 [Jekyll](https://github.com/mojombo/jekyll)，正如 [Livid](http://livid.v2ex.com/essays/2012/01/18/say-hello-to-jekyll/) 所说，在任何一个网页端写作，体验都是令人沮丧的。

目前整个 Blog 的运作，包含以下几个关键字：Jekyll，[Dropbox](http://db.tt/AbTUZFF)，[Markdown](http://daringfireball.net/projects/markdown/)，Cron。

* 在服务器上安装 Dropbox，并与本地的 Dropbox 帐号共享指定目录；
* 本地使用 [Mou.app](http://mouapp.com/) 以 Markdown 格式写作，写完后存放于 Dropbox 的共享目录中，Dropbox 负责把这些内容同步到服务器；
* 服务器上开启一个 Cron 任务，自动运行 Jekyll 把写好的内容发布成网页；