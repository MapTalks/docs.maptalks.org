---
layout: docs
title: 基于DB2的数据库配置
permalink: /docs-cn/db-ibm-db2/
---

# DB2

DB2存在多种JDBC驱动，不同的情况需要不同的JDBC驱动，[这里](http://www-01.ibm.com/support/docview.wss?uid=swg21363866)参阅相关说明

```javascript
{
    "name": "db2-based",
    // 数据库类型
    "type": "db2",
    // 主机
    "host": "localhost",
    // 端口，50000为DB2的默认端口
    "port": 50000,
    // 数据库名称
    "database": "testdb",
    // jdbc连接参数
    "parameters": "",
    // 用户名
    "username": "db2admin",
    // 访问密码
    "password": "db2admin",
    // 连接池配置，覆盖默认连接池配置中的相应参数
    "pool": {
        "initialSize": 3,
        "driverClassName": "com.ibm.db2.jcc.DB2Driver"
    }
}
```
