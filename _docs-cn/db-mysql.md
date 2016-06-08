---
layout: docs
title: 基于MySQL的数据库配置
permalink: /docs-cn/db-mysql/
---

# MySQL

```javascript
{
    "name": "mysql-based",
    // 数据库类型
    "type": "mysql",
    // 主机
    "host": "localhost",
    // 端口，3306为mysql的默认端口
    "port": 3306,
    // 数据库名称
    "database": "testdb",
    // jdbc连接参数
    "parameters": "?useUnicode=true&characterEncoding=utf-8",
    // 用户名
    "username": "root",
    // 访问密码
    "password": "root",
    // 连接池配置，覆盖默认连接池配置中的相应参数
    "pool": {
        "initialSize": 5,
        "maxActive": 50
    }
}
```
