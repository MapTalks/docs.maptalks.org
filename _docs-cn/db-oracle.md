---
layout: docs
title: 基于Oracle的数据库配置
permalink: /docs-cn/db-oracle/
---

# Oracle
```javascript
{
    "name": "oracle-based",
    // 数据库类型
    "type": "oracle",
    // 主机
    "host": "localhost",
    // 端口，1521为Oracle的默认端口
    "port": 1521,
    // Oracle数据库的SID
    "database": "orcl",
    // jdbc连接参数
    "parameters": "",
    // 用户名
    "username": "orcluser",
    // 访问密码
    "password": "orcluser",
    // 连接池配置，覆盖默认连接池配置中的相应参数
    "pool": {
        "initialSize": 3
    }
}
```
