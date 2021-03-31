---
layout: post
title: 开启 Firefox 的单窗口模式
categories: ['text']
tags: ['Firefox','Browser']

---

以前总是用T[abbrowser Extensions](https://addons.mozilla.org/extensions/moreinfo.php?id=158)来实现Firefox的单窗口模式，其实在config里面也可以很方便的设置：

* 输入地址 "about:config"
* 搜索 browser.tabs.showSingleWindowModePrefs
* 双击，把值改为 "true"
* 重启 Firefox 
* 打开设置面板
* 高级 -> 标签浏览
* 选中 "链接在新标签打开"
* 再次重启 Firefox