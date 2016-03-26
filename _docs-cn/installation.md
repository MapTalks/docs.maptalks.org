---
layout: docs
title: 安装
permalink: /docs-cn/installation/
---

## 安装前提

* [Node.js](http://nodejs.org) 4+
* [Java SE](http://www.oracle.com/technetwork/java/javase/overview/index.html) 6+

## MapTalks安装

两种安装方式: npm安装(推荐[cnpm](https://github.com/cnpm/cnpm),速度会快很多), 下载安装

### NPM安装

1. 安装

**注意**: 必须添加-g参数即全局安装方式
```bash
npm install -g maptalks-cli
```
2. 初始化
```bash
cd /home/foo/
maptalks init mapapp
# init后的目录结构
/home/foo/mapapp
    |- www
        |-maptalks.js
        |-maptalks.css
        |-images+
    |- db
        |-default.db
    |- logs
    |- tiles
        |- sample+
    |- maptalks.json
```
### 下载安装

1. 在[这里](http://www.maptalks.org/download)根据操作系统下载相应版本.
2. 解压到某个目录下, 例如 /home/foo/maptalks
3. 运行start.sh (windows下运行start.bat)