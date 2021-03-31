---
layout: post
title: IE 的 text-indent Bug
categories: ['text']
tags: [Frontend,CSS,IE,Browser]

---

今天遇到的一个 Bug，主要表现为：当容器的第一个子元素为 inline 属性，并且为该子元素定义了 text-indent 的话，IE 渲染出错。

####实例 1

	<div style="margin: 10px auto; padding: 10px; width: 400px; border: 3px solid #EEE;"> 
		<span style="background: #FF0; color: red; text-indent: 50px;">Indent</span> 
    	正文 
	</div>

在 Firefox 中，渲染正常：

![image](/assets/images/ie-inline-indent-bug-firefox-01.png)

在 IE6 中，错误：

![image](/assets/images/ie-inline-indent-bug-ie-01.png)

错在 text-indent 只在 block 级别的元素中体现，在本例中的 span 元素中，应予忽略。

####实例 2

给 span 加个浮动，让它自动成为 block 元素看看。

	<div style="margin: 10px auto; padding: 10px; width: 400px; border: 3px solid #EEE;"> 
    	<span style="float: left; background: #FF0; color: red; text-indent: 50px;">Indent</span> 
    	正文 
	</div>

在 Firefox 中，渲染正常：

![image](/assets/images/ie-inline-indent-bug-firefox-03.png)

在 IE6 中，错误：

![image](/assets/images/ie-inline-indent-bug-ie-02.png)

错在 span 将自身的 text-indent 属性传递给了它的父元素 div。

####实例 3

负值的 text-indent 会是怎样呢？

	<div style="margin: 10px auto; padding: 10px; width: 400px; border: 3px solid #EEE;"> 
    	<span style="background: #FF0; color: red; text-indent: -9999px;">Indent</span> 
    	正文 
	</div>

在 Firefox 中，渲染正常：

![image](/assets/images/ie-inline-indent-bug-firefox-01.png)

在 IE6 中，错误，我们什么也看不到了：

![image](/assets/images/ie-inline-indent-bug-ie-03.png)

错在 span 不但将自身的 text-indent 属性传递给了它的父元素 div，而且还将超出的内容隐藏了，在没有定义 overflow 属性时，元素的默认 overflow 属性应该是 visible。

####实例 4

既浮动，又负值的 text-indent 呢？（事实上我正是在这种情况下遭遇了这个 Bug）：

	<div style="margin: 10px auto; padding: 10px; width: 400px; border: 3px solid #EEE;"> 
    	<span style="float: right; margin-left: 5px; width: 40px; background: #FF0; color: red; text-indent: -9999px;">Indent</span> 
	    正文 
	</div>

在 Firefox 中，渲染正常：

![image](/assets/images/ie-inline-indent-bug-firefox-04.png)

在 IE6 中，仍然是错误：

![image](/assets/images/ie-inline-indent-bug-ie-04.png)

依然是 span 将自身的 text-indent 属性传递给了它的父元素，并将超出的内容隐藏了。

以上的 Bug 在 IE8 的“IE7 mode”中得到了部分修正，当 span 为浮动时基本是正常的，但默认情况下仍然错误。其他版本未测试。