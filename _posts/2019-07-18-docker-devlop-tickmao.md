---
layout:     post
title:      "停止、删除docker容器和镜像"
subtitle:   "docker命令"
date:       2019-07-18 10:00:00
author:     "Tickmao"
header-style: "text"
catalog:     true
tags:
    - 编程
    - docker
    - 命令
    - 容器
    - 镜像
---

最近在使用服务器中，因为部分配置内容出现错误，需要对docker的容器和镜像进行删除，重新配置，记不住docker删除等命令常常需要查询，之前已经有过同样的情况，所以对命令进行记录，以便将来直接进行查询。

对docker主要是对container（容器）和image（镜像）进行清理。

### container（容器）

列出所有container（容器）ID

```bash
docker ps -aq
```

查看所有运行或者不运行container（容器）

```bash
docker ps -a
```

停止所有的container（容器）

```bash
docker stop $(docker ps -aq)
```

删除所有的container（容器）

```bash
docker rm $(docker ps -aq)
```

停止、启动、杀死、重启一个容器

选择对应容器ID即可

```bash
docker stop ID
docker start ID
docker kill ID
docker restart ID
```

删除所有停止的容器

```bash
docker container prune
```

删除所有不使用的镜像

```bash
docker image prune -f -a
```

但是只删除容器无法清除干净，再进行配置会容易出现问题。所以还需要删除image（镜像）。

### image（镜像）

查看当前image（镜像）

```bash
docker images
```

删除全部image（镜像）

```bash
docker rmi $(docker images -q)
```

强制删除全部image（镜像），和其他一样，增加-f，如下：

```bash
docker rmi -f $(docker images -q)
```

当然docker还有很多需要学习，在此只是列举些日常的一些使用命令，避免下次查询重复，方便自己查询。熟能生巧，当使用更加熟悉之后，形成肌肉记忆就可有可无了。

**—ChangLog**

2019.07.18

- 博客初拟