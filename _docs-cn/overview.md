---
layout: docs
title: 了解MapTalks
permalink: /docs-cn/overview/
---

## MapTalks功能分类

MapTalks的功能分为以下几类：

* tile，地图底图服务， 各种格式地图底图数据的读取、发布
* 空间数据库功能，图层(FeatureLayer)操作， 位置数据([Feature](https://en.wikipedia.org/wiki/Feature_data))的增删改查。
* 空间计算， 空间关系判判断、 空间分析方法（Buffer/ContextHull/Intersection等）

## 接口形式

接口形式： HTTP RestFul

请求数据格式： JSON， [GeoJSON](http://www.geojson.org)作为Feature的数据格式

## 技术栈

MapTalks基于以下技术开发：

* Java: 
    * [Jetty](https://github.com/eclipse/jetty.project): Servlet容器
    * [Druid](https://github.com/alibaba/druid): 数据库连接池
    * [FastJSON](https://github.com/alibaba/fastjson): JSON处理 
    * [JTS](https://github.com/dr-jts/jts): 空间分析和拓扑计算
* Node.js: 初始化、服务启动和停止
    * PM2: 进程管理
    
## 功能列表

```
Tile
|
```