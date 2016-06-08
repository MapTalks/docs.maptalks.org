---
layout: docs
title: 基于PostgreSQL的数据库配置
permalink: /docs-cn/db-postgresql/
---

# PostgreSQL/PostGIS
```javascript
{
    "name": "postgresql-based",
    // 数据库类型
    "type": "postgresql",
    // 主机
    "host": "localhost",
    // 端口，5432为PostgreSQL的默认端口
    "port": 5432,
    // 数据库名称
    "database": "testdb",
    // jdbc连接参数
    "parameters": "",
    // 用户名
    "username": "postgresql",
    // 访问密码
    "password": "postgresql",
    //连接池配置，覆盖默认连接池配置中的相应参数
    "pool": {
        "initialSize": 3
    }
}
```
