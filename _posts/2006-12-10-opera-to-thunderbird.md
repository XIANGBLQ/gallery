---
layout: post
title: 将 Opera M2 邮件文件转换至 ThunderBird
categories: ['text']
tags: [Browser,Opera,Thunderbird]

---

Opera的[M2](http://www.opera.com/products/desktop/m2/)与Mozilla的[ThunderBird](http://www.mozilla.com/en-US/thunderbird/)都是很不错的免费邮件客户端软件。我前段时间一直使用M2，因为公司邮件服务器配置更改，导致发不出邮件，所以想试试ThunderBird（后来知道不是邮件客户端的问题），所以从网上找了一下将M2的邮件导出到ThunderBird的方法。其实操作很简单，我是这么理解的：M2支持将邮件导出为.mbs文件，事实上其文件结构是UNIX通用的邮件格式，而这种文件格式对ThunderBird来说也是可用的。

详细的操作方法可以参考[这篇文章](http://www.tomwalsham.com/post.php?id=66)，在这里备忘一下：

1. 将M2中需要导出的邮件导出为“exported.mbs”文件（右键，导出），备用。
2. 在ThunderBird中新建一个文件夹“imported”，退出ThunderBird。
3. 打开ThunderBird的存档文件夹，例如c:/Documents And Settings/YOUR_USER/Application Data/Thunderbird/Profiles/xbsfhafaf.default/Mail/pop.yourPOPserver.com/在这个目录下，我们可以看到有一个“imported.msf”文件和一个没有扩展名的“imported”文件，其中没有扩展名的的这个文件就是用来存储邮件的，现在把它删除，把之前导出的“exported.mbs”拷贝到这个目录中来，重命名为“imported”（不要有扩展名）。
4. 运行ThunderBird，应该可以看到之前导出的邮件已经在“imported”文件夹中了。