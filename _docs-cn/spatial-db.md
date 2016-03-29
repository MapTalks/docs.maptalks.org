---
layout: docs
title: 安装
permalink: /docs-cn/spatial-db/
---

# 空间数据库的使用

MapTalks的空间数据库功能包括：

* 空间数据库的初始化
* 图层的创建、删除、修改和查询
* 空间数据的插入、删除、修改和查询
* 结合空间条件与属性条件的数据查询

MapTalks中由rest模块来负责空间数据库的所有功能。

## 典型的空间数据库应用过程

以下以最常用的SQL数据库为例， 列举空间数据库的一个典型应用过程：

* 初始化空间库，载入必须的配置表和图层表。
* 创建一个图层， 图层有很多种类型， 最常用的类型是db_table，即用一个数据库表作为图层。
* 为图层添加自定义属性，这些属性可用来查询， 在db_table类型图层中， 自定义属性就是数据表列。
* 向图层插入空间数据
* 根据业务系统需要， 根据空间查询条件和业务属性查询条件查询空间数据
* 返回数据并展现

## 空间数据库功能的调用方式

MapTalks在rest模块中用HTTP RestFul API接口的形式提供服务。

实际应用中可以通过以下几种方式调用：

* 通过HTTP接口直接调用， 例如通过浏览器的Ajax请求、各语言的HTTP客户端程序等。
* 通过客户端SDK开发包
    * [JAVA客户端](https://github.com/MapTalks/maptalks.java)
    * [Javascript(Browser/Node.js)客户端](https://github.com/MapTalks/maptalks.client.js)

## 功能说明

### 空间库初始化

空间库初始化的目的是在数据库中创建必要的配置表, 包括:
* 配置表 maptalks_gis_config, 包含版本号, 坐标参考系(CRS)等必要配置
* 图层表 maptalks_gis_layer, 空间库中的图层均记录该表中

例如我们想在MySQL数据库中创建一个空间库， 步骤如下：

* 在MySQL中创建一个数据库， 例如 testdb
```sql
CREATE DATABASE testdb;
```
* 参考[这里](configuration-db.html)， 在maptalks.json配置文件中增加对testdb的连接实例
* 调用MapTalks的rest服务接口， 初始化空间库， 以调用java sdk为例：
```java
//host MapTalks服务的主机
//port MapTalks服务的端口号
//空间库， 即maptalks.json中数据库连接实例的name
MapDatabase db = new MapDatabase("localhost",8090,"testdb");
//采用GCJ02作为默认的坐标参考系
db.install(new InstallSettings(CRS.GCJ02));
```

### 图层管理