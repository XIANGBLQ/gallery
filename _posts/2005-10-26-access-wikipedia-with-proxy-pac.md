---
layout: post
title: 利用代理脚本访问维基百科
categories: ['text']
tags: [GFW,Wikipedia]

---

说是这周三有希望解禁，但是现在还没有看到什么变化。这里有一个在Firefox下用代理脚本访问的解决方案，权且用一下吧。

<!--more-->

	function FindProxyForURL(url, host) {
		url = url.toLowerCase();
		host = host.toLowerCase();
		if(dnsDomainIs(host,"wikipedia.org")) return "PROXY 145.97.39.132:80";
		else return "DIRECT";
	}
	
把这段文本保存为proxy.pac，然后选择Firefox的工具/选项/连接设置/选择自动代理配置，输入proxy.pac的路径，如："C:\Program Files\Mozilla Firefox\plugins\proxy.pac"，然后载入设置，ok。

由于维基的图片是在wikimedia.org域中的，所以按照上述方法处理后，图片仍然显示不出来，我在配置文件中加了这么一行：

	else if(dnsDomainIs(host,"wikipedia.org")) return "PROXY 145.97.39.132:80";