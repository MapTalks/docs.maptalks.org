---
layout: docs
title: 基于文件的数据库配置
permalink: /docs-cn/db-file/
---

# File

MapResty支持基于文件系统的空间库，文件空间库是一个本地文件夹，其中包含了:
* 一个JSON格式的空间库配置文件`db.json`
* 图层数据文件，支持`shapefile`和`GeoJSON`数据

文件空间库只支持`file_shp`和`file_geojson`类型图层， 不支持其他的图层类型。
* [Shapefile](https://en.wikipedia.org/wiki/Shapefile)是[ESRI](http://www.esri.com/)公司发布的空间数据文件格式， 其采用二进制形式存储， 是目前最流行的空间数据存储文件格式。
* [GeoJSON](http://www.geojson.org)是一个基于JSON格式的空间数据格式，其采用文本形式存储，是http服务中最流行的空间数据交换格式。

一个典型的文件空间库文件夹结构
```bash
    .
    |- db.json
    |- shp
    |   |- layer1.shp # shapefile空间数据文件
    |   |- layer1.dbf # shapefile属性数据文件
    |- geojson
    |   |- layer2.geojson # geojson数据文件
```

## 配置参数
```javascript
{
    // 实例名称， 供查询程序引用
    "name": "file-based",
    // 数据库类型，这里为file
    "type": "file",
    // 数据文件根目录，如果是相对路径，则相对的是config.json所在的目录
    "database": "./db/filedb"
}
```

## db.json示例
```javascript
{
    // 空间库的crs
    "crs": "gcj02",
    // 版本
    "version": "1.0",
    // 图层列表
    "layers": [
        {
            // 图层id
            "id":         "layer1",
            // 图层类型，shapefile类型图层
            "type":       "file_shp",
            // 数据文件路径
            "source":     "shp/layer1.shp",
            // file_shp图层的配置属性
            "properties": {
                // 文件编码，默认是UTF-8
                "encoding": "UTF-8",
                // 载入的DBF属性列表，字符串类型， 以逗号(,)分隔
                "property": "prop1, prop2, prop3"
            }
        },
        {
            // 图层id
            "id":         "layer2",
            // 图层类型，geojson类型图层
            "type":       "file_geojson",
            // 数据文件路径
            "source":     "geojson/layer2.geojson",
            // file_geojson图层的配置属性
            "properties": {
                // 文件编码，默认是UTF-8
                "encoding": "UTF-8"
            }
        }
    ]
}
```
