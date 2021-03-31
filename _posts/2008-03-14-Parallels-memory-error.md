---
layout: post
title: Parallels Desktop 内存分配错误
categories: ['text']
tags: [Tools]
---

启动 Parallels Desktop 时候偶尔会出现这样的错误：

	Unable to allocate memory for monitor PE!

应该是虚拟机启动时，分配内存错误，在 Parallels 的官方论坛上，[看来出现这个问题的人还不少](http://forums.parallels.com/printthread.php?t=17831)，貌似还没有很好的解决方法。这应该是一个 Bug，因为我的机器内存已经升级到 4G，而且是在启动其他程序前启动的 Parallels，应该不会是内存不够用。

我的建议是，出现这个错误后，不要再尝试关闭 Parallels 后重新启动，否则迎接你的极可能是一次四国。你要做的是重启电脑，然后在开启其他程序前先启动 Parallels Desktop 虚拟机。