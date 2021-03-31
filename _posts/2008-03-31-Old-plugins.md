---
layout: post
title: 让老版本的扩展应用运行在新本浏览器上
categories: ['text']
tags: [Browser]

---

浏览器要升级，新版本带来的新特性让人忍不住想尝鲜，那些旧的扩展（插件)怎么办？

事实上，有相当一部分的扩展或插件跟浏览器自身的版本关系不大，稍微修改下这些插件内部的一两个文件，使他在浏览器启动的时候能够被加载，基本上就能使用。

<!--more-->

**Firefox 的 Extension 可以这样修改：**

* 把下载到的 `.xpi` 文件改为 `.zip` 压缩包；
* 解压缩，在得到的文件夹中找到 `install.rdf` 文件；
* 用文本编辑器打开，修改 `<em:maxVersion>3.1.0</em:maxVersion>` 这一行，将中间那个数值调大一些；
* 保存后，将刚才解压缩得到的文件重新压缩（注意文件结构)，然后将扩展名该回 `.xpi`；
* 将最终的 `.xpi` 文件拖到 Firefox 的扩展管理面板，安装。

**Safari 的 Plugin 可以这样修改：**

* 找到 Plugin 的存放位置，一般在 `/Library/Application Support/SIMBL/Plugins` 目录下，`.bundle` 格式；
* 右键点击目标 Plugin , 选择“`显示包内容`”；
* 用文本编辑打开 `Info.plist`，编辑 `<key>MaxBundleVersion</key>` 这一行下面 `<string>5550</string>` 中的数值，调大一些；
* 有时也需要同样调整 `Resources/Info.plist` 文件；