---
layout: post
title: CSS background-positon 属性中百分比数值的使用
categories: ['text']
tags: ['CSS']

---

大部分人应该习惯于使用描述性词语（left、top、center…）或者数值（20px、1em…）对背景图片定位，百分比可能比较少用，常见的有50%、100%等数值。例如希望背景图片水平居中，距离容器顶部20px，可以使用

	background-position: 50% 20px;

之所以不使用

	background-position: center 20px;

是因为类似这种描述性词语和数值混用的形式不被W3C推荐。（**单纯的描述性词语组合使用是没有问题的，例如：background-position: right bottom;**）

<!--more-->

使用百分比进行定位的好处是可以利用CSS的计算功能，达到px定位所难以完成的任务。例如在一个宽高均为300px的容器中，使用

	background-position: 150px 150px;

可以看到背景图片的左上角顶点（坐标0,0）定位到了齐容器的中心点（坐标150px,150px）。

![image](http://fangming.li/wimgs/blog/background_position_px.png)

而把150px替换为50%，使用

	background-position: 50% 50%;

看到的并**不是**如下的效果

![image](http://fangming.li/wimgs/blog/background_position_incorrect.png)

而是这样

![image](http://fangming.li/wimgs/blog/background_position_percent.png)

可见，CSS计算出了背景图片的中心点。这也可以解释为什么我们在使用

	background-position: 100% 100%;

定位的时候，图片被放置在容器的右下角，而并没有跑出容器。（如果使用 background-position: 300px 300px; 的话，背景图片会被移出容器）

同样，如果使用

	background-position: 20% 20%;

会将背景图片的坐标点(20%,20%)定位到容器的坐标点(20%,20%)。

![image](http://fangming.li/wimgs/blog/background_position_20.png)