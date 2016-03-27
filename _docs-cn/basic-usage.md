---
layout: docs
title: 基本使用
permalink: /docs-cn/basic-usage/
---

# 基本使用

MapTalks安装完毕后, 会为操作系统的命令行终端生成一个全局命令: maptalks-server。

maptalks-server命令的基本用法：

```bash
$ maptalks-server init mapapp
# 初始化一个maptalks运行目录， 即maptalks运行所需的文件和配置
# 一个初始的maptalks运行目录结构如下：
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
```

```bash
$ maptalks-server start /path/to/maptalks.json
# 启动maptalks-server服务

$ maptalks-server stop /path/to/maptalks.json
# 停止maptalks-server服务

```

