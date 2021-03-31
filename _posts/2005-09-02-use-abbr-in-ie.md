---
layout: post
title: 让 IE 支持 abbr 标签
categories: ['text']
tags: [Frontend,CSS,IE]

---

`<abbr>` 是一个表示一个词或短语的简称（如“HTML”）的标签，通常同时使用title属性来指出原词或原意。但是这个标签一直以来没有得到IE的支持。今天在网上看到了这个解决方案，作者[Dean Edwards](http://dean.edwards.name/)一再声明“This is not a hack”。

解决方案：在文档头部

	<html xmlns="http://www.w3.org/1999/xhtml">

中做如下改动

	<html xmlns:html="http://www.w3.org/1999/xhtml";>

然后，把原来的

	<abbr title="abbreviation">abbr<abbr>

改为

	<html:abbr title="abbreviation">abbr</html:abbr>