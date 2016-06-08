---
layout: docs
title: 基于Sqlite的数据库配置
permalink: /docs-cn/db-sqlite/
---

# SQLite/Spatialite

SQLite和Spatialite是基于文件系统的嵌入式数据库， 很适合数据量不大、用户量不大应用场景。

例如演示系统、一些内部地图系统等。

另因为SQLite和Spatialite数据文件的便携性， 也很适合用于数据的导入导出、分发和备份等。

SQLite/Spatialite的配置方法:

```javascript
{
    // 实例名称， 供查询程序引用
    "name": "sqlite-based",
    // 数据库类型
    "type": "sqlite",
    // sqlite的数据文件路径
    // 如果是相对路径， 则相对的是config.json所在的目录
    "database": "./db/default.db"
}
```
