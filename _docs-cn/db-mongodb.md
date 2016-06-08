---
layout: docs
title: 基于MongoDB的数据库配置
permalink: /docs-cn/db-mongodb/
---

# MongoDB

使用MongoDB的geospatial功能支持比较完备的[GeoJSON类型](https://docs.mongodb.com/manual/applications/geospatial-indexes/#geojson-objects)的话，需要`MongoDB >= 2.6`

```javascript
{
    "name": "mongodb-based",
    // 数据库类型
    "type": "mongo",
    // 主机
    "host": "localhost",
    // 端口，27017为MongoDB的默认端口
    "port": 27017,
    // 数据库名称
    "database": "testdb",
    // 用户名
    "username": "mongo",
    // 访问密码
    "password": "mongo"
}
```
