---
layout: post
categories: ['text']
---

说到 IE 的 bug，一个臭名昭著的例子是它对于“盒模型”的错误解释：在 IE5.x 以及 Quirks 模式的 IE6/7 中，将 border 与 padding 都包含在 width 之内。这为前端工程师的工作平添了不少麻烦，几户每个需要定义尺寸的 box 都要思量一下：是否触发了“盒模型 bug”？

同时，由于另一撮浏览器对标准的遵从，我们在精确定义一个在有限空间内显示的 box 时，也需要计算一下：留给它的空间只有那么大，刨去 border 和 padding，我们该把它的 width 写成多少呢？

这种情况在 CSS3 时代有了改善，得益于这个叫做 box-sizing 的属性，它具有“content-box”和“border-box”两个值。

定义 box-sizing: content-box; 时，浏览器对盒模型的解释遵从我们之前认识到的 W3C 标准；
定义 box-sizing: border-box; 时，浏览器对盒模型的解释与 IE6 相同；

![image](http://fangming.li/wimgs/blog/css3-box-sizing.png)

为什么说这个属性“迟来”呢？IE 对于盒模型的解释固然不符合 W3C 的规范，但是也有它的好处：无论如何改动 border 与 padding 的值，都不会导致 box 总尺寸发生变化，也就不会打乱页面整体布局。而在 Firefox 等现代浏览器下，如果我们要改变一下 padding 的值，就不得不重新计算 box 的 width。现在 [IE6 寿终正寝](http://warm-journey-42.heroku.com/)，这个 CSS 属性未免有些姗姗来迟。

试用这个新属性，Firefox 请使用 -moz-box-sizing，Safari / WebKit 请使用 -webkit-box-sizing，Opera 直接用 box-sizing 即可。