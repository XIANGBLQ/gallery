---
layout: post
title: 利用 Javascript 为 Blogger 页面加上标题
categories: ['text']
tags: ['Javascript','Blogger']

---

在使用了 Blogger 系统的 Blog 中，存档页面和 Label 页面都没有一个醒目的标题，看起来跟首页没有什么两样，这对于阅读者来说多少有些不友好。如果能够给每个页面加一个标题，例如“存档：2006/11 - 2006/12”或者“TAG：Javascript”，那么阅读者就会减少很多迷惘（~~本站的演示:Label页面、存档页面~~）。这个功能只需了解一下  Javascript 中的 location 对象就不难实现。

<!--more-->

以URL

	http://www.mixfog.com/blog/index.htm?action=view#comment

为例，看一下 location 对象的几个常用属性：

**Javascrit location Object**

	属性			值				备注
	hash		comment			即我们平时所说的“锚点”链接
	host		www.mixfog.com	主机名
	hostname	mixfog.com		与host相同，有时会省略www
	href		http://www.mixfog.com/blog/index.htm	完整的URL
	pathname	/blog/index.htm	URL中hosthost之后的内容
	port						端口信息，通常都是空的
	pritocol	http:			协议
	search		?action=view	查询字符串

看了这个表之后，基本上能够总结出一个解决方案了。Blogger中生成的Label页面的URL都是

	http://Blog地址/labels/labelName.htm

用 Javascript 很容易就可以得到这个 labelName。

同样，如果设置了存档文件的目录为“archives”，文件名为 archive.htm 的话，一个存档页面的 URL 应该类似

	http://Blog地址/archives/2006_11_01_archive.htm

也会很容易的获得“2006_11_01”这个字段作为存档页面的标题。但是有一个更好的途径，利用存档页面的 &lt;title&gt;，Blogger 生成的存档页面的 &lt;title&gt;大多是“网站名称:存档时间”，这个存档时间的格式是由个人在后台设置的，例如本站为“2006/11 - 2006/12”。

那么看一下具体的代码：

	function getPageTitle() {
		var pathName = location.pathname; //获得页面路径
		if (pathName.indexOf('/labels/')!=-1) { //判断是否为Label页面 
			var fileName = pathName.split('/labels/');
			var tagName = fileName[1].split('.');
			document.write ('<h1>TAG: '+ tagName[0] +'</h1>');
		} else if (pathName.indexOf('/archives/')!=-1) { //判断是否为存档页面 
			var pageTitle = document.title.split(':');
			document.write ('<h1>存档: '+ pageTitle[1] +'</h1>');
		}
	}

代码很简单，基本上没什么好说的，然后在模板中调用 getPageTitle 即可。由于只在 Label 页面和存档页面用到，所以 ItemPage 就完全不需要这段代码：

	<MainOrArchivePage><script type="text/javascript"> getPageTitle(); </script><MainOrArchivePage>

把这段代码加在模板中希望出现页面标题的位置即可，本站的演示可参考“Label页面”、“存档页面”。有几个需要注意的地方：

* 存档的路径会因为个人设置的不同而不同，这不难解决。
* 本例中假设站点名称中不包含半角的冒号，因为存档页的时间和站点标题是用半角冒号来分割的，但即使包含，也不难解决。
* 第三个有点致命，不支持中文的 Label，因为 Blogger 对中文的 Label 进行的转码，例如“电影”，对应的 Label 页面地址可能是“55S15b2x.htm”，好在我的 Blog 中尽量少用中文的 Label 名称，所以这个问题就有待其他人士来解决吧。
* 补充一个，如果您的 Label 中含有空格，在 URL 中会自动转换为 20%，在获取的时候就需要转换回来，但是个人不建议在 Label 中使用空格，用一个连字符“-”也许更好。