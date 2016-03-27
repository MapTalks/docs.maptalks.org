---
layout: docs
title: 使用
permalink: /docs-cn/usage/
---

# 使用

MapTalks安装完毕后, 会为操作系统的命令行终端生成一个全局命令: `maptalks-server`。

MapTalks的所有功能都可以通过 `maptalks-server` 命令行完成。

`maptalks-server`命令用法：

* 运行目录初始化

运行目录存放了`maptalks-server`运行时所需的配置文件、示例数据、www服务的静态资源(例如客户端地图程序maptalks.js)等。
```bash
$ maptalks-server init mapapp
```
初始的运行目录结构如下：

{% highlight bash %}

    .
    |- www
    |   |-maptalks.js
    |   |-maptalks.css
    |   |-images+
    |- db
    |   |-default.db
    |- logs    
    |- tile
    |   |- sample
    |- maptalks.json
    |- package.json
{% endhighlight %}

* 启动服务

```bash
$ maptalks-server start /path/to/maptalks.json
```

* 停止服务

```bash
$ maptalks-server stop /path/to/maptalks.json
```

* 注册系统服务

```bash

```

* 注销系统服务

```bash

```