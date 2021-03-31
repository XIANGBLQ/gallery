---
layout: post
title: Opera 9.x max-width Bug
categories: ['text']
tags: ['CSS','Browser']

---

max-width和disply:table-cell是非常好用的两个CSS属性。利用max-width和max-height，可以非常方便的将网页中的图片缩小到一定尺寸，而且保证较小的图片不会被放大，图片的宽高比例也不会被强行改变。而disply:table-cell和其他的disply:table等属性结合，可以用div等标签模拟出table的结构，对于页面的排版也非常有用。

<!--more-->

但是现在看来，Opera(9.00)对max-width的解释有些跟其他浏览器不一致。如果一个图片的原始宽度是300px，在CSS中定义它的max-width为100px，Opera确实能够按照max-width的值显示，但是这个图片在页面中所占据的实际位置却仍然按照原始宽度300px来计算。这点在普通情况下不太明显，一旦把图片放置在一个disply为table-cell的元素中，例如常规的td，或者是disply定义为table-cell的div或其他元素，问题就出来了。Opera会依照图片的原始宽度，把table-cell撑开到300px，虽然显示的图片只有100px宽。而高度却显示正常。阅读全文...

下图说明了Firefox对这种情况的显示方式，这也正式我们希望的：

![image](http://fangming.li/wimgs/blog/max-width-firefox.png)

而Opeera却是这样显示的：

![image](http://fangming.li/wimgs/blog/max-width-opera.png)

这里有一个实例，您可以在不同的浏览器中查看本页的显示结果，当然，不要对IE抱有太大的希望。

![image](http://fangming.li/wimgs/blog/sampleimg_300_300.jpg)

这是一张原始图片，尺寸为300px/300px，我们把它max-width和max-height都定义为100px：

	img {
		max-width: 100px;
		max-height: 100px;
	}

把它放置在一个宽度和高度均为200px的单元格td中：

	td {
		width:200px;
		height:200px;
		vertical-align: middle;
		text-align: center;
		background: #F5F3FF;
		border: 1px solid #CCC7E1;
	}

![image](http://fangming.li/wimgs/blog/sampleimg_300_300.jpg)

把它放置在一个disply为table-cell，宽度和高度均为200px的span标签中，之所以选择span标签，是为了更能体现出IE的显示效果，另外，span之外需要有一个display为table的元素，我们选用一个div：

	span {
		disply: table-cell;
		width:200px;
		height:200px;
		vertical-align: middle;
		text-align: center;
		background: #F5F3FF;
		border: 1px solid #CCC7E1;
	}

![image](http://fangming.li/wimgs/blog/sampleimg_300_300.jpg)