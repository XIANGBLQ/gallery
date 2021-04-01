## DotsTheme

一款极简 Jekyll 主题，倘若你更想关注内容其本身，欢迎尝试使用本主题，部分功能开箱即用，其他的待支持功能 （参照主题特性），等我后续慢慢更新吧……

### Preview

#### [View dotstheme Boilerplate &rarr;](https://dotstheme.tickmao.com/)

![1](https://ae01.alicdn.com/kf/H74dae26854d14a7db7dbc7e5fd2b3505t.jpg)

![2](https://ae01.alicdn.com/kf/H292d22c5bce7462690840b5d7671af56Q.jpg)

### 主题特性

- [x] 主题基于 `jekyll 4.0` 开发
- [ ] 响应式布局
- [x] 支持黑暗模式切换
- [ ] 支持字体大小修改
- [x] 文章时间线索引
- [x] 支持9种主题代码高亮
- [x] 支持 `dispus` 、 `Gittalk` 二种评论系统
- [x] 支持 `百度统计` 、`谷歌分析` 两种网站追踪系统

### 开始使用

#### 线上部署

首先在 `github` 上开启一个仓库起名为 `你的github用户名.github.io` 。并 `clone` 你的仓库到本地。 然后下载 `dotstheme` Zip到本地去修改

```
$ git clone https://github.com/tickmao/dotstheme.git
```

将 `_config.yml` 文件更改为自己的配置（下面会介绍）。之后，将所有文件拷贝至自己的本地仓库根目录下，再上传至自己的 `github` 线上仓库，即可通过域名 `https://你的github用户名.github.io` 访问看到自己的博客页面。

#### 本地部署

首先在本地安装 `Jekyll` [详情请戳](https://www.jekyll.com.cn/docs/quickstart/)

安装完成之后，使用命令 `jekyll -v` 查看 jekyll 版本 ，若低于 `jekyll 4.x.x` 则尽量升级至 `jekyll 4.x.x`及以上 。

使用 `gem install jekyll-paginate` 或 `sudo gem install jekyll-paginate` 安装Jekyll的分页插件。

将源码 `clone` 到本地后，在终端进入 `dotstheme` 根目录，运行 `jekyll server` 或 `bundle exec jekyll serve` ，即可开启jekyll的服务。通过浏览器访问 [http://localhost:4000](http://localhost:4000) ，即可看到本地部署的 `dotstheme` 博客了。

> ​	由于本主题是基于 `jekyll 4.0.0` 开发 ，jekyll的版本差异也许会导致相关显示效果的差异。详情请参考官方文档：[news](https://jekyllrb.com/news/)
### 说明文档

- 开始
  - [关于博客](#关于博客)
  - [写文章](#写文章)
- 组件
  - [个人信息](#个人信息)
  - [社交媒体](#社交媒体)
  - [首页显示](#首页显示信息)
  - [导航栏](#导航栏)
  - [分页](#分页)
  - [代码高亮](#代码高亮主题)
  - [页脚](#页脚)
  - [评论系统](#评论系统)
  - [统计信息](#统计信息)


> ​	通用修改 `_config.yml` 文件，你便可以轻松搭建属于你自己的个人博客。一部分配置，默认已经是配置好的，你只需要修改下面列出的内容即可完成搭建。
#### 关于博客

```yaml
---
# Site settings 配置站点
title: 'your awesome title'
description: 'your web description'
keywords: 'your web keywords, another keywords'
url: 'https://abc.github.io' # your host
---
```

`title` ：用于页面的 title 标签的显示内容

`description` ：网站的简介

`keywords` ：网站的关键词

`url` ：网站域名

#### 写文章

博客通过解析 `markdown` 文件来部署文章页面的，所以用户写文章只需要写一篇 markdown，并放置在站点根目录下的 `_post` 文件夹即可。具体的 markdown 语法自行上网搜索学习，或使用 markdown 编辑器进行写作。推荐一款 markdown 编辑器：[typora](https://www.typora.io) 。支持 windows 、mac OSX 、Linux 。`drafts`文件夹下为草稿，默认不展示。

关于文章 YAML 头信息：

```yaml
layout: post
title:  "post title"
subtitle: 'post subtitle'
date:   2020-02-29 08:44:13
description: ''
```

#### 个人信息

该部分显示在 `colophon` 文件夹，修改对应的`md`文档即可。

#### 社交媒体

请在`nav.html`中修改对应的链接

#### 首页显示信息

首页主要显示最近的10篇文章

#### 导航栏

```yaml
# nav 中文字符空格：&emsp;
nav: # 最佳体验 五到八个标签
  首页: '/'
  归档: '/archive/'
  作品: '/project/'
  关于: '/colophon/'
  RSS: '/feed'
```
默认依据 `Page title` 全部展示，当然如果想要自己添加删减，按照格式调整即可。

#### 分页

```yaml
# 分页
paginate: 10
paginatepath: ['page:num']
```

随个人爱好在，填写你需要的在首页最多显示多少篇博客的数字。

本地部署的需要使用 `gem install jekyll-paginate` 或 `sudo gem install jekyll-paginate` 安装 Jekyll 的分页插件。

#### 代码高亮主题

```yaml
# 代码高亮 使用rouge
highlighter: rouge
# 代码高亮主题使用pygments主题: autumn\ default\ emacs\ friendly\ manni\ murphy\ pastie\ perldoc\ tango 任选一个你喜欢的主题名称填在下面的单引号中
pygmentsTheme: 'default'
```

代码高亮使用 jekyll4.0 之后的默认高亮引擎 `rouge` 。关于主题，只需要在 `pygmentsTheme` 后填写喜欢的主题名称即可。共有9款主题可选，主题名见上文。

代码高亮的写法：

~~~markdown
```css
*{
 margin:0;
 padding:0;
}
```
~~~

#### 页脚

```yaml
# since
footer:
  since: 2020
```

在 footer.html 修改`run_date`的时间，用于页脚显示时间，可以根据自己的实际情况显示网站的运行时间。

#### 评论系统

```yaml
# disqus 评论
disqus: false
disqus_username: user-id  # disqus_username: 你的用户名
# Gittalk 评论 OAuth Application
gittalk: false
gittalk_owner: ''  # github用户名
gittalk_admin: ''  # github用户名
gittalk_repo: ''   # github博客存放的仓库名
client_id: ''      # 注册 OAuth Application 后获得的 client_id
client_secret: ''  # 注册 OAuth Application 后获得的 client_secret
# ​按申请第三方评论是获取的相关信息在配置文件中进行填写即可。
```

出于显示样式与中国大陆网络环境考虑。更推荐 `Gittalk`

#### 统计信息

```yaml
# 百度统计 在 baidu-url 里填写自己相关的 url 代码
baidu: false
baidu-url: '' #填写自己相关的 url 代码
# 谷歌分析 在 google-ID 里填写自己在谷歌分析获得的追踪ID
google: false
google-ID: '' #Format: UA-xxxxxx-xx
```

在 `baidu-url` 和 `google-ID` 分别填上注册获取的相关信息。使用 `true` 或者 `false` 开启或关闭他们。出于中国大陆网络环境，默认关闭百度统计，当然可以多开。

## 声明

你可以自由的 fork。如果你能将主题作者和 github 的地址保留在你的页面底部，我将非常感谢你。

如果你喜欢我的这个博客模板，请在 dotstheme.github.io 这个 repository 点个赞（右上角 star 一下）。

主题仅用于个人学习或使用，如有疑问请联系作者。E-mail：[lyle.lypm@gmail.com](mailto:lyle.lypm@gmail.com)

## 参与我们

如果有任何想法或需求，可以在 [issue](https://github.com/tickmao/dotstheme/issues) 中告诉我，欢迎各种小伙伴踊跃留言。

## Author

DotsTheme ©[Tickmao](https://www.tickmao.com), Released under the MIT License.

Blog @[Tickmao](https://blog.tickmao.com) · GitHub @[Tickmao](https://github.com/tickmao) · Twitter @[Tickmao]
