---
layout: post
title: 利用 CSS 实现双线边框
categories: ['text']
tags: ['Frontend','CSS']

---

**首先声明，这篇文章中所讲的实例使用到了浏览器的 Bug，这是不被推荐的，仅供大家参考一下。或者在确认这个方案对整个网站的整体效果影响不大的时候，可以小用一下。**

我们都知道，在 CSS 默认的边框属性中，有 double 这个值，代表双线，但是在实际运用中，效果并不理想，两层边框只能使用一种颜色，而且各个浏览器的解释也略有差异。

<!--more-->

在一次工作实例中，我本想给 &lt;button&gt; 添加一个背景图片，做一个好看点的按钮，却发现 IE 在显示 &lt;button&gt; 的背景图片时，存在一个 Bug：IE 总是在 &lt;button&gt; 的边框和背景图之间，显示 1px 宽的间隙，间隙的颜色由 &lt;button&gt; 的背景颜色决定。

这个发现非常好玩，本来 &lt;button&gt; 只有一层边框，现在看起来就像是内外两层边框了。这样不就可以做出双层边框效果的按钮了吗。不过说到底，这只是 IE 的 Bug，其他的现代浏览器在显示 &lt;button&gt; 的背景图片时，还是非常标准的，不存在这 1px 的间隙。好在 CSS 2有另外一个属性：outline，这个属性理所当然的不被 IE 支持，Firefox，Opera，Safari 等浏览器的当前版本都可以正常显示它。这样，我们就可以有一个方案了：

* 对于IE，使用border做外边框，使用Bug中提到的1px间隙做内边框
* 对于现代浏览器，使用outline做外边框，使用border做内边框

如下图所示：

![image](http://fangming.li/wimgs/blog/outline-bg-image.png)

经过美化后的CSS方案：

	button {
		line-height: 40px;
		color: #1e3182;
		background: #FFF url(button_bg.png) repeat-x 0 0;
		padding: 0 1.5em 0 2em;
		letter-spacing: 0.5em;
		cursor: pointer;
	}
	*>button { /*for modern browser*/
		height: 40px;
		outline: 1px solid #9DAAE2;
		border: 1px solid #FFF !important;
	}
	* html button { /* for IE 6.0/IE 5.* */
		border: 1px solid #9DAAE2;
	}
	*+html button { /* for IE 7 */
		border: 1px solid #9DAAE2 !important;
	}

这个方案的优点是：

* 可以随意变换双层边框的颜色，内外边框可以不同
* 按钮的宽度不用定死，由其内部的文字多少来决定
* 按钮所用到的图片只是很窄的一幅背景图

当然缺点就是双线边框中的内边框在IE下只能是1px，而且由因IE修补Bug而导致方案失效的危险。

您可以在~~这个页面~~看到实例，虽然由于浏览器的其他原因，显示的效果略有差异：IE 6 高出了 3px，IE 7.0 又矮了两个象素，而且IE显示的宽度都比实际定义的宽出一些，但双线的效果总算都还可以接受。