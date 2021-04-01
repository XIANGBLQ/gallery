---
layout:     post
title:      "编程 | js制作网页运行时间显示"
subtitle:   "博客运行时间"
date:       2019-06-09 15:00:00
author:     "Lyle"
header-img: "img/post-bg-jstimedate.jpg"
header-mask: 0.5
catalog:     true
tags:
    - 编程
    - js
    - time
    - 有趣
    - 学习
---

# JS制作网页运行时间展示

![image-20190609143111777](https://ae01.alicdn.com/kf/HTB1Www.b.GF3KVjSZFv762_nXXa4.png)

浏览网页意外的看到一些博客的网页底部显示博客倒计时，觉得很有意思，就想将其加入到我的博客下方。

> 我们常常记录自己时间的分布，也希望赋予其应有的意义。

## 功能背景

为记录博客生命周期，树立自己的小目标成就。

## 设计思路

通过 `现在时间 - 建站时间`的方式，就可以获得时长。我们把天数减去之后，剩下的就是小时，再减去就是分钟... 以此类推就可以得到我们想要的结果。

## 实现方式

利用 `Unix 时间戳` 来进行处理，`Date.parse()` 支持将字符串直接转换成时间戳（需要除去 1000 才是正确的结果），在后面计算天数的时候有一个数字是 `864e5`，这个数字其实就是 `86400000` 的简写。

## Js代码

```js
function run_date(date){
// 建站日期
var created = Date.parse(date);
// 现在时间
var now = new Date().getTime();
// 存活时间
var cha = now - created;
// 有多少天
var day = cha / 864e5;
// 取整数输出天
var day_c = Math.floor(day);
// 减去整数的天，得出剩下的小数，并变成小时（1 天等于 24 小时）
var hour = 24 * (day - day_c);
// 取整数输出小时
var hour_c = Math.floor(hour);
// 减去剩下的小时，得出剩下的小数，几分钟（1小时等于60分）
var min = 60 * (hour - hour_c);
// 取整数输出分钟
var min_c = Math.floor(min);
// 剩下的就是秒，直接取整
var sec = Math.floor(60 * (min - min_c));
return "博客已萌萌哒存活 <a>" + day_c + "</a> 天 <a>" + hour_c + "</a> 小时 <a>" + min_c + "</a> 分 <a>" + sec + "</a> 秒";
}

setInterval(function () {
    document.querySelector(".foot-date").innerHTML = run_date("2019/1/1");
}, 1000);

function add_zero(num){
    if(num.toString().length < 2){
        num = "0" + num;
    }
    return num;
}
```

## 前端显示

放置在blog页面，需要修改footer文件，在想要显示的位置创建一个`div`或者`span`标签，并设置对应的类名。如：

```html
<span class="foot-date">博客已萌萌哒存活 <a>?</a> 天 <a>?</a> 小时 <a>?</a> 分 <a>?</a> 秒</span>
```

## 实现效果

![image-20190609144319291](https://ae01.alicdn.com/kf/HTB1N7Z_b79E3KVjSZFG76319XXaL.png)

**—ChangLog**

2019.06.09

- 博客初拟