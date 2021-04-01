---
layout:     post
title:      "Windows上打造漂亮的终端"
subtitle:   "终端美化指南"
date:       2019-08-08 17:10:00
author:     "Tickmao"
header-img: "img/post-bg-terminal.jpg"
header-mask: 0.5
catalog:     true
tags:
    - Terminal
    - Powershell
    - Windows
    - Fluent Terminal
    - 终端美化
---

## Windows上打造漂亮的终端

经常使用 Mac 的用户因为有着 iTerm2 && Oh My Zsh 组合搭建的效果舒适终端使用体验，可是当更换平台至 Windows 时感到一直没有合适的终端效果而遗憾。

最近很热门的提到了 Windows 平台终于有着自己的 Terminal 而炒得热火朝天，但在本人尝试之后，发现其当前还并不够稳定。经常会出现崩溃的情况，抱着折腾了这么久但却没有发现一款合适的终端工作台怎么都不合适, Windows 平台上怎么能有没有优秀的终端出现的心态。

心心念念，必有回响，于是发现了今天的主角 Fluent Terminal 。

我之前也玩过 Cmder，虽说比起自带的 cmd 已经强大了很多，但是效果比 iTerm 还是差不少，总感觉不得劲。Fluent Terminal 其友好的效果却一度让我以为回到了 Mac 上的操作体验。

### 最终效果图

![Fluent Terminal](https://ae01.alicdn.com/kf/H57388934b93240c38d3678a6ba46e0e6d.png)

### 详细配置

#### 下载 Fluent Terminal

[项目地址](https://github.com/felixse/FluentTerminal)

1.你可以通过 releases 直接下载安装包，解压之后使用 PowerShell 执行文件 Install.ps1 即可。

2.当然你可以通过 [Chocolatey](https://chocolatey.org/install) 进行安装。使用 Powershell 执行

```zsh
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1')); choco feature enable -n allowGlobalConfirmation
```

安装完成后，使用 `choco -v` 命令验证 Chocolatey 是否已正确安装.

![choco](https://ae01.alicdn.com/kf/H156a2205ec7c46bea8e9952d95b108bch.png)

进入合适软件安装目录，执行 `choco install fluent-terminal` 下载 Fluent Terminal 。

#### 安装 oh-my-posh

`oh-my-posh` 是一个强大的 powerline 主题，类似于 Linux下的 `oh-my-zsh` .

相应的 Github 官方项目 [oh-my-posh](https://github.com/JanDeDobbeleer/oh-my-posh) 中其实有具体的操作步骤

```zsh
Install-Module posh-git -Scope CurrentUser
Install-Module oh-my-posh -Scope CurrentUser
```

想要配置生效，需要创建 PowerShell 的配置文件，通过记事本打开执行 `notepad $PROFILE`。当然如果你安装了 vscode ，也可以通过 `code $PROFILE` 打开。个人推荐使用后者vs code，记得安装vscode时勾选上 `Add to PATH (available after restart)`

```zsh
if (!(Test-Path -Path $PROFILE)) {New-Item -Type File -Path $PROFILE -Force}
notepad $PROFILE
```

在配置文件中新增如下几行：

```zsh
Import-Module posh-git
Import-Module oh-my-posh
Set-Theme Sorin #我使用的主题Sorin，按照你选择的主题设置即可
$DefaultUser = ' 你的用户名 ' #想要隐藏本机用户名还可以添加这行，设置个人用户名
```

#### 安装字体

使用终端用户，编辑器用的比较多的字体可能是 [Source Code Pro](https://github.com/adobe-fonts/source-code-pro) 或者 [FiraCode](https://github.com/tonsky/FiraCode) ，系统安装对应字体后，在设置中选择使用。

其他可依据个人喜好在 Fluent Terminal 中设置对应的选项即可。

#### 隐藏配置显示

因为每次打开都需要提示加载个人和系统配置文件的时间，为了显示更加简洁，可以对软件进行设置，只需要在软件
设置 > 配置文件 > Powershell > 编辑

将参数项填写 -nologo 即可。


**ChangLog**

2019.08.08

- 博客初拟

2019.12.25

- 更新隐藏配置显示
