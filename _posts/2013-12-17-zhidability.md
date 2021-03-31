---
layout: post
title: Zhidability
categories: ['text']
tags: ['Tools','Zhihu']
---

无法忍受阅读知乎的时候字体太小，以及一直显示的顶部横条，仿照 Readability 早期的做法，做了个 Bookmarklet，以解此忧。

<a href="javascript:(function()%7Bvar%20head%20%3D%20document.getElementsByTagName('head').item(0)%3Bvar%20body%20%3D%20document.getElementsByTagName('body').item(0)%3Bvar%20style%20%3D%20document.createElement('style')%3Bstyle.type%20%3D%20'text%2Fcss'%3Bstyle.innerHTML%20%3D%20%22body%7Bfont-family%3A'Hiragino%20Sans%20GB'%2C'Helvetica%20Neue'%2CHelvetica%2CArial%2CSans-serif%7D.zu-top%2C.zu-footer%2C.zu-main-sidebar%2C.zm-tag-editor%2C.zu-edit-button%2C.zm-editable-tip%2C.zm-item-link-avatar%2C.zm-item-vote-info%2C.zh-answers-title%2C.zh-backtotop%7Bdisplay%3Anone!important%7D.zu-main-content-inner%7Bmargin%3A0%20120px!important%7D.zu-question-my-bio%7Bfont-weight%3A100%3Bcolor%3A%23BBB%7D.zm-item-title%7Bfont-size%3A24px!important%7D%23zh-question-detail%7Bcolor%3A%23999%7D.zm-item-answer%20.zm-item-rich-text%7Bpadding%3A20px%200%2050px%7D.answer-head%7Bpadding-top%3A20px%7D.zm-item-meta%7Bfont-size%3A12px%3Bopacity%3A0%7D.zm-item-answer%3Ahover%20.zm-item-meta%7Bopacity%3A1%7D.zm-votebar%7Bmargin-top%3A70px%7D%23lu-remove-style%7Bposition%3Afixed%3Btop%3A0%3Bright%3A40px%3Bbackground%3Ared%3Bcolor%3A%23FFF%3Bpadding%3A6px%2012px%7D%23lu-remove-style%3Ahover%7Btext-decoration%3Anone%7D%23zh-question-answer-wrap%2C.zm-item-answer-author-wrap%7Bfont-size%3A16px%7D%22%3Bhead.appendChild(style)%3Bvar%20removeStyle%20%3D%20document.createElement('a')%3BremoveStyle.href%20%3D%20'%23'%3BremoveStyle.onclick%20%3D%20function()%7Bhead.removeChild(style)%3B%7D%3BremoveStyle.id%20%3D%20'lu-remove-style'%3BremoveStyle.innerHTML%20%3D%20'%26%23215%3B'%3Bbody.appendChild(removeStyle)%7D)()">Zhidability</a>

![Zhidability](/assets/images/zhidability.png)

使用的时候别忘了知乎默认提供的 J K 快捷键。