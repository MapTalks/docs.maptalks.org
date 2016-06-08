---
layout: docs
title: 基于MS-SQL-Server的数据库配置
permalink: /docs-cn/db-ms-sql-server/
---

# Microsoft SQL Server
```javascript
{
    "name": "mssql-based",
    // 数据库类型
    "type": "mssql",
    // 主机
    "host": "localhost",
    // 端口，1433为SQL Server的默认端口
    "port": 1433,
    // 数据库名称
    "database": "testdb",
    // jdbc连接参数
    "parameters": "",
    // 用户名
    "username": "sa",
    // 访问密码
    "password": "sa",
    // 连接池配置，覆盖默认连接池配置中的相应参数
    "pool": {
        "initialSize": 3
    }
}
```
