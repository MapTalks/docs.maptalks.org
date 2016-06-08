---
layout: docs
title: 数据库参数配置
permalink: /docs-cn/configuration-db/
---

MapResty具备将数据存入空间数据库，和在空间数据库上进行空间查询的能力。

# 支持的数据库

MapResty目前支持将以下数据库或数据文件作为空间库存储：

* [File (只读)](db-file)
    * Shapefile
    * GeoJSON
* [SQLite/Spatialite](db-sqlite)
* [MySQL](db-mysql)
* [PostgreSQL/PostGIS](db-postgresql)
* [MongoDB](db-mongodb)
* [MicroSoft SQL Server](db-ms-sql-server)
* [Oracle](db-oracle)
* [DB2](db-ibm-db2)

# 数据库参数配置示例

空间数据库配置在[config.json](configuration.html)中的`database`配置项， 如下所示：

```javascript
...
"database" : {
    // 数据库连接实例配置
    "instances": [
        // 第一个数据库连接实例
        {
            // 实例名称，供查询程序引用
            "name": "default",
            // 数据库类型，这里为sqlite
            "type": "sqlite",
            // sqlite数据文件
            "database": "./db/default.db"
        },
        // 第二个数据库连接实例
        {
            // 实例名称， 供查询程序引用
            "name": "file",
            // 数据库类型，这里为file
            "type": "file",
            // 数据文件根目录
            "database": "./db/filedb"
        },
        // 第三个数据库连接实例
        {
            "name": "mysql",
            // 数据库类型，这里是mysql
            "type": "mysql",
            // 主机
            "host": "localhost",
            // 端口
            "port": 3306,
            // 数据库名称
            "database": "testdb",
            // jdbc连接参数
            "parameters": "?useUnicode=true&characterEncoding=utf-8",
            // 用户名
            "username": "root",
            // 访问密码
            "password": "root",
            // 连接池配置
            // 这里设置的参数会覆盖默认连接池配置中的相应参数
            "pool" : {
                "initialSize": 5,
                "maxActive": 50
            }
        }
    ],
    // 默认连接池配置
    "pool": {
        "initialSize": 2,
        "maxActive": 20,
        "maxWait": 60000,
        "timeBetweenEvictionRunsMillis": 60000,
        "minEvictableIdleTimeMillis": 300000,
        "validationQuery": "SELECT 'x'",
        "testWhileIdle": true,
        "testOnBorrow": false,
        "testOnReturn": false,
        "poolPreparedStatements": true,
        "maxPoolPreparedStatementPerConnectionSize": 20
    }
}
...
```
