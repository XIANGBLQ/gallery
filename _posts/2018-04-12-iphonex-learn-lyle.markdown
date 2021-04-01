---
layout:     post
title:      "规范论 | iPhone X 设计指南"
subtitle:   "产品设计"
date:       2018-04-12 22:20:00
author:     "Lyle"
header-img: "img/post_bg_iphonexdesign.jpg"
header-mask: 0.5
catalog:     true
tags:
    - 规范
    - ios
    - 产品
    - 设计
    - 学习
---

# iPhone X 设计指南

随着iPhone X的越来越普及，苹果开始要求ios应用需适配iPhone X才可上线，熟读设计规范，可有有效的在产品设计初期避免不必要的麻烦，将问题扼杀在摇篮当中。

iphone X的到来标志着ios 11的到来。一个更高的手机，全面屏。有着比5.5英寸iphone 8 plus更大的5.8英寸的OLED屏幕，但是整体尺寸却和iphone 8一样。对于设计师来说，我们在我们的画布上有更多的自由了。

## 更高的屏幕

额外的145pt能放下额外的一行内容或者是加一个菜单，曾经这样可能会造成界面太拥挤的情况。尽管有不同的解决方案，iphone 8和iphone 8plus 因为有这相同比列的屏幕。
[![image](https://user-images.githubusercontent.com/17292115/37010837-674b9df4-2128-11e8-9709-8d14926272d4.png)](https://user-images.githubusercontent.com/17292115/37010837-674b9df4-2128-11e8-9709-8d14926272d4.png)

## 内容有更多的空间

相比与原先的iphone，高度增加了惊人的332pt，相当于7个导航栏的高度。内容变得更有想象的空间，[左滑菜单]([https://developer.apple.com/videos/play/wwdc2014/211/)，不再那么常见。当你把iphone X 和旧iphone放在一起，你会发现高度上的空间几乎翻倍了。总之，这意味着如今的应用都会包含状态栏，导航栏，标签栏和home指示器。省略这些不仅用户体验会变得糟糕，这会使得你的应用和苹果官方的应用截然不同。
[![image](https://user-images.githubusercontent.com/17292115/37010873-8fe2d246-2128-11e8-9fe9-300cf827475c.png)](https://user-images.githubusercontent.com/17292115/37010873-8fe2d246-2128-11e8-9fe9-300cf827475c.png)

## 齐刘海

设计上最有争议的部分是头部10%得区域。传感器区域，也成为齐刘海，它使得iphone X的屏幕称不上真正的全面屏。技术上，还不可能去除它，因为它包含了面部识别所需的设备、摄像机和扬声器。设计上，这是苹果公司近年来制造的最大的争议。但是看了其他手机制造商的[解决方案](https://twitter.com/DesaiRaj414/status/917416673497440257)，也有着类似的前额或者下巴，不能说它们就没有争议。
苹果官方[反对](https://developer.apple.com/ios/human-interface-guidelines/overview/iphone-x/)，使用黑色的条来隐藏齐刘海。他们解释，尽管齐刘海可能是麻烦的，但是还是有足够的空间给状态栏和其他内容。它和底下的内容有了过渡和一种屏幕更大了的感觉。
像墙纸、地图和颜色等元素不会因为圆角和齐刘海的轻微裁剪而受损。就像[视屏](https://developer.apple.com/videos/play/fall2017/801/)中所说，通过隐藏的方式，你的应用会显得很小，并和其他的应用格格不入。
[![image](https://user-images.githubusercontent.com/17292115/37011686-2403a290-212c-11e8-9b87-6c56f1e72918.png)](https://user-images.githubusercontent.com/17292115/37011686-2403a290-212c-11e8-9b87-6c56f1e72918.png)

## 更大的标题

在ios11中一屏的标题通常是34pt。它们被设置为半粗体的黑色。有趣的是当你滚动屏幕的时候，标题会过渡到导航栏上，这还给了用户有价值的空间。横向模式时，它在导航条上保持很小的状态。这给了设计师们很清晰的认识，第一，利用额外的空间；第二，你的设计需要自适应，因为额外的空间不一定在横向和竖向下都存在。
[![image](https://user-images.githubusercontent.com/17292115/37012030-9723ce66-212d-11e8-81b0-4f64154de3c8.png)](https://user-images.githubusercontent.com/17292115/37012030-9723ce66-212d-11e8-81b0-4f64154de3c8.png)
ps: [gif](https://github.com/shenxiang11/blog/blob/master/gif/d33994b1-6644-454e-8b60-affe9726a090.gif)

## 更大的状态栏

状态栏高度从20pt增加到了44pt。通知现在能被从左上角拖出来。中控台能从右上角滑出。从底部快速滑动能回到首页。或者终止滑动能够打开应用导航。
[![image](https://user-images.githubusercontent.com/17292115/37012196-685302ae-212e-11e8-9a99-b6587db1ec54.png)](https://user-images.githubusercontent.com/17292115/37012196-685302ae-212e-11e8-9a99-b6587db1ec54.png)
ps：[gif](https://github.com/shenxiang11/blog/blob/master/gif/3ecac839-aafd-4108-a213-005d165c7710.gif)

## 安全区域布局指导

当为iphone X设计时，注意圆角和齐刘海会裁剪内容。任何时候都应该避免这现象。使用安全区域布局指导，在齐刘海遮挡不到的地方放置内容，这样能保证内容不被裁剪。通常，背景不必遵循这个规则，而图片、按钮、文字应该遵循此规则。
[![image](https://user-images.githubusercontent.com/17292115/37012275-f0dcb1ec-212e-11e8-8010-d703e4de9cc9.png)](https://user-images.githubusercontent.com/17292115/37012275-f0dcb1ec-212e-11e8-8010-d703e4de9cc9.png)

## 横向的iphone X

横向时，状态栏会隐藏，来最大化显示内容。导航栏高度减小到32pt，标签栏高度30pt，home指示器23pt。即使大部分用户不会使用横向模式，但这仍然是很重要的使用情况。例如，看一张横向的照片，一部全屏的视屏和阅读很多文字的文章。完成这些后，他们会习惯于切换回正常模式，尤其是当设备卡顿了。
如果你的设备已经适配了ipad，为什么不去适配横向的iphone呢？小的效果能有大的收获，所有的现代应用都应该是自适应的。
[![image](https://user-images.githubusercontent.com/17292115/37012413-719b8312-212f-11e8-9e53-13ca85d71f36.png)](https://user-images.githubusercontent.com/17292115/37012413-719b8312-212f-11e8-9e53-13ca85d71f36.png)

## 横向下的网站

如果你是网站的产品经理。iphone X横向时，你的网站左右会有很多的空白。因为，安全区域被自动应用了以避免内容被裁剪，这样其实是很糟糕的。为了避免这一情况，苹果官方出了一份[指南](https://webkit.org/blog/7929/designing-websites-for-iphone-x/)来让网站适配横向的iphone X。一般地，把背景铺满全屏，而不是仅仅在安全区域内部。
[![image](https://user-images.githubusercontent.com/17292115/37012592-73561f7c-2130-11e8-813d-718c14aa6dd6.png)](https://user-images.githubusercontent.com/17292115/37012592-73561f7c-2130-11e8-813d-718c14aa6dd6.png)

## 圆角

裁剪现象也会出现在iphone X的圆角区域。只要你隐藏了状态栏和home指示器就会出现这种情况。但是，应用几乎都是全屏使用的，比如照相机，距离边角有一定的外边距是很重要的。为了完美的和圆角边界契合，推荐给按钮设置16pt的外边距。
[![image](https://user-images.githubusercontent.com/17292115/37012725-0919da62-2131-11e8-8f95-61470ce50ebf.png)](https://user-images.githubusercontent.com/17292115/37012725-0919da62-2131-11e8-8f95-61470ce50ebf.png)

## 在iOS模拟器中预览你的应用

iphone X设备还没有发布。机遇就在发布后，它可能会卖的很好，我们大多数人可能一时间买不到。除了手上的真实设备，唯一的体验方式是通过iOS模拟器。你能通过[XCode](https://developer.apple.com/xcode/)来浏览你的应用和网站。
[![image](https://user-images.githubusercontent.com/17292115/37012831-98de86ac-2131-11e8-8218-1d41151fd6e2.png)](https://user-images.githubusercontent.com/17292115/37012831-98de86ac-2131-11e8-8218-1d41151fd6e2.png)

## 滑动菜单的消亡

十年间，设计师要为旧iphone的小屏幕紧凑地排版。大多数设计师选择直接省略标签栏，因为它占据了太多横向的空间。有一些人有创造力地发明了，从左滑出的按钮。这就是著名的滑动导航的诞生。起初它是有趣的清新的，但它是一个可用的恶魔。越来越多点击需要到达额外的屏幕。结果，这意味着次要的标签栏越来越少的使用。人们经常会忘记还有更多的内容。
随着大屏出现，单手使用是一种痛苦。苹果甚至以双击home键的方式来切换，以免手指摸不到导航条。左滑菜单占据了屏幕的左上角，所以去点击菜单是令人沮丧的。屏幕更高，内容空间不再是问题。标签栏明显是能更好地替换左滑菜单，因为有了更多的空间。iphone X紧跟这一趋势。如果你有超过一对区域，没有理由不用标签栏。iOS11中，横向时，标签栏占据更小的空间。网页中左滑菜单是常见的，可能的一个原因是web的体验还跟不上原生的体验。Reactive Native是一个出色的web技术来使用原始组件。但是，在iOS中尤其是iphone X你还是应该使用标签栏。
[![image](https://user-images.githubusercontent.com/17292115/37013364-6cfee7c2-2134-11e8-8547-a52fa63f525c.png)](https://user-images.githubusercontent.com/17292115/37013364-6cfee7c2-2134-11e8-8547-a52fa63f525c.png)
ps：[gif](https://github.com/shenxiang11/blog/blob/master/gif/1a4da67f-850a-4055-a41f-96d296cdbfc9.gif)

## 自适应布局和多任务处理

有越来越多的设备[分辨率](http://www.paintcodeapp.com/news/ultimate-guide-to-iphone-resolutions)，让你的布局是响应式的很重要。使用诸如SKetch的[约束](https://www.sketchapp.com/docs/layer-basics/constraints/)和XCode的[自动布局](https://developer.apple.com/library/content/documentation/UserExperience/Conceptual/AutolayoutPG/index.html)，你要以一种屏幕尺寸是弹性的方式去设计，如果需要可以显示额外的菜单。

#### STACK VIEWS

在XCode中，你会发现[STACK VIEWS](https://developer.apple.com/videos/play/wwdc2015/218/)，一个神奇的工具能够让你的布局更好的应对变化。相同的元素和组能够动态地堆在一起，你需要做的就是编辑它们的间隙，和决定内容是如何填充盒子的。然后你可以用自动布局来完成工作。苹果推进优先使用STACK VIEWS，其次是使用Auto Layout
[![image](https://user-images.githubusercontent.com/17292115/37015871-8d793c9a-2144-11e8-9343-213548cbcbf6.png)](https://user-images.githubusercontent.com/17292115/37015871-8d793c9a-2144-11e8-9343-213548cbcbf6.png)

## 点和像素

开发者用点，所以理解和像素有什么不同很重要。当iPhone问世时，两个单位是相同的，1pt等于1px。然后，随着视网膜屏的到来，1pt成了2px。所以iphone的点和像素的关系依赖于像素密度(iPhone 4, 5, 6, 7, 8 = [@2x](https://github.com/2x), iPhone 8 Plus, iPhone X = [@3X](https://github.com/3X))。为了更好理解点和像素的不同，我强烈推进观看此[视频](https://vimeo.com/169809377)。
[![image](https://user-images.githubusercontent.com/17292115/37015992-11dc0472-2145-11e8-9ae2-c19668bcc0f3.png)](https://user-images.githubusercontent.com/17292115/37015992-11dc0472-2145-11e8-9ae2-c19668bcc0f3.png)

## iPhone分辨率

iPhone有五种主要分辨率: 320 x 480 pt (iPhone 4S), 320 x 568 pt (iPhone SE), 375 x 667 pt (iPhone 8), 414 x 736 pt (iPhone 8 Plus) and 375 x 812 pt (iPhone X)。布局并不是等比缩放，而是加长了分辨率。例如，导航栏只是边宽了而没有变高。里面的元素保持原封不动。
iPhone 8plus是唯一一部，横向操作像iPad一样的iPhone。换句话说是左侧导航出现，而不是使用标签栏。
[![image](https://user-images.githubusercontent.com/17292115/37016164-dfb35d46-2145-11e8-8304-50cca534a9fc.png)](https://user-images.githubusercontent.com/17292115/37016164-dfb35d46-2145-11e8-8304-50cca534a9fc.png)

## iPhone尺寸类型

尺寸类型允许我们给屏幕的长和宽分类，并基于这些情况设置条件约束。例如，我们规定在紧凑的宽度下使用30pt*30pt的头像，在正常宽度下使用50pt*50pt，只是应为大尺寸屏幕有更大的空间。由于布局在横向和纵向是截然不同，iPhone和iPad之间也是，尺寸类型是自动布局约束你的布局必不可少的。
高和宽有3中尺寸类型：Compact, Regular and Any。通过组合它们，我们立刻能适配我们的各种设备。例如Compact (width) x Regular (height) 的组合只会在iPhone竖向时生效，不会影响横向和iPad。
有趣的是 Compact x Compact将会影响出了iPhone 6+, 7+, 8+外的处于竖向的iPhone，即使它的屏幕相当宽。所以，熟悉不同的组合很重要，下图是说明。
[![image](https://user-images.githubusercontent.com/17292115/37016292-730a5ac2-2146-11e8-927b-bbc195af6dc9.png)](https://user-images.githubusercontent.com/17292115/37016292-730a5ac2-2146-11e8-927b-bbc195af6dc9.png)

## 应用图标

应用图标用来彰显你的品牌。用户体验应用时，首先看到的就是它。在主屏幕上、应用商店里、Spotlight和设置中显而易见。

#### 支持

[@1x](https://github.com/1x)的素材iPhone不再支持，所以你不必生成它们。应用图标现在有两种分辨率[@2x](https://github.com/2x)和[@3X](https://github.com/3X)。有三种类型应用图标、Spotlight和设置。对于iPad，[@1x](https://github.com/1x)和[@2x](https://github.com/2x)仍然在使用。
[![image](https://user-images.githubusercontent.com/17292115/37016652-52fb232c-2148-11e8-9709-41a0a51baef5.png)](https://user-images.githubusercontent.com/17292115/37016652-52fb232c-2148-11e8-9709-41a0a51baef5.png)

#### 超级圆角

从iOS7以后，圆角从普通的变成了更加圆润。注意，不要到处有遮罩的图标，否则你可能得到一个黑色的产物。只要到处正方形给应用就可以了。
[![image](https://user-images.githubusercontent.com/17292115/37016783-ef012a6e-2148-11e8-8738-d4493ec0c516.png)](https://user-images.githubusercontent.com/17292115/37016783-ef012a6e-2148-11e8-8738-d4493ec0c516.png)

#### 图标网格

苹果给图标设置了黄金比例。这保证了图标是主角并且有一个好的比列。这是一个好的规则，但是不是一个强行的规则。甚至它们的应用也都省略了。
[![image](https://user-images.githubusercontent.com/17292115/37016848-3549c242-2149-11e8-9bdb-2c0fef303333.png)](https://user-images.githubusercontent.com/17292115/37016848-3549c242-2149-11e8-9bdb-2c0fef303333.png)

## 颜色

iOS的按钮有着生动的颜色。这些颜色在白色和黑色背景上表现的都很好。注意颜色应是比较少的应用，比如交互元素上和导航栏上。10%-20%我们的设计上和颜色有关，多了它们会强走用户对内容的注意力。
iOS通常使用中立的颜色给背景和菜单区域。白底黑字的强烈对比很适合阅读。最后柔和的蓝色使得按钮显得突出。
[![image](https://user-images.githubusercontent.com/17292115/37016972-aa3ceaf2-2149-11e8-9584-d33e1eac3e3f.png)](https://user-images.githubusercontent.com/17292115/37016972-aa3ceaf2-2149-11e8-9584-d33e1eac3e3f.png)

## 系统字体

如今的系统[字体](https://developer.apple.com/fonts/)，小于20pt的是SF Pro Text，其他情况下是SF Pro Display。当要使用系统字体时，你有了动态的选择基于用户的偏爱。
[![image](https://user-images.githubusercontent.com/17292115/37017151-6ba03bd6-214a-11e8-890a-e14914a1ab5c.png)](https://user-images.githubusercontent.com/17292115/37017151-6ba03bd6-214a-11e8-890a-e14914a1ab5c.png)

## 按钮和字体

一般的规则是按钮44pt，小字字号12pt，正文17pt，标题20pt。
[![image](https://user-images.githubusercontent.com/17292115/37017267-f203bf18-214a-11e8-8c6f-019fef6088da.png)](https://user-images.githubusercontent.com/17292115/37017267-f203bf18-214a-11e8-8c6f-019fef6088da.png)

## 空白和对齐

通常规则是至少8pt的内边距或外边距。这会很舒适，阅读体验较好。同时，文字和元素应该基于基线对齐。
[![image](https://user-images.githubusercontent.com/17292115/37017323-3d4baab2-214b-11e8-8011-1813dded54f3.png)](https://user-images.githubusercontent.com/17292115/37017323-3d4baab2-214b-11e8-8011-1813dded54f3.png)

## 状态栏

尽可能在所有情况下保留状态栏，用户依赖它来获取信号、电视和时间的信息。状态栏的文字和图标颜色可以是黑色和白色，但是背景能制作成和导航栏混合的任意颜色。
[![image](https://user-images.githubusercontent.com/17292115/37017389-7c287aee-214b-11e8-97fc-7373a34631b3.png)](https://user-images.githubusercontent.com/17292115/37017389-7c287aee-214b-11e8-97fc-7373a34631b3.png)

## 导航栏

------

[![image](https://user-images.githubusercontent.com/17292115/37017514-db32ecd6-214b-11e8-80fd-3c5a45735418.png)](https://user-images.githubusercontent.com/17292115/37017514-db32ecd6-214b-11e8-80fd-3c5a45735418.png)

#### 相关链接

[原文](https://designcode.io/ios11-iphone-x)

**—ChangLog**

2018.04.12

- 博客初拟
