---
layout: docs
title: 安装
permalink: /docs-cn/installation/
---

#安装

MapTalks的安装有两种方式: 
* npm (推荐[cnpm](https://github.com/cnpm/cnpm),速度会快很多) 
* 安装包安装

## 安装前提

安装MapTalks前, 需要安装以下软件:

* [Node.js](http://nodejs.org) 4+

## 方式一: NPM

采用npm安装时, 您需要安装以下软件以运行MapTalks

* [Java SE](http://www.oracle.com/technetwork/java/javase/overview/index.html) 6+

安装命令:

**注意**: 必须添加-g参数, 即全局安装方式
```bash
npm install -g maptalks-server
```

## 方式二: 安装包

1. 在[这里](http://www.maptalks.org/download)根据操作系统下载相应版本.
2. 解压到某个目录下, 例如 /home/foo/maptalks-server
3. 在/home/foo/maptalks-server下运行npm start