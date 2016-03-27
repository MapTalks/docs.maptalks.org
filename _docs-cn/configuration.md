---
layout: docs
title: 安装
permalink: /docs-cn/configuration/
---

# 配置

MapTalks 允许在一台服务器上运行多个MapTalks 服务实例， 每个服务实例各自拥有独立的运行目录。

运行目录可以用 `maptalks-server init [dir]` 生成， 例如：

```bash
maptalks-server init mapapp
# 运行目录结构
    .
    |- static
    |   |-maptalks.js
    |   |-maptalks.css
    |   |-images+
    |- db
    |   |-default.db
    |- logs    
    |- tile
    |   |- sample
    |- maptalks.json
    |- package.json
```

## maptalks.jso配置说明

每个MapTalks运行目录中只有一个配置文件， 即根目录下的 `maptalks.json`

初始的maptalks.json内容如下：

```javascript
{
    "server" : {
        "listenOn": "0.0.0.0",
        "port" : 8090,
        "logLevel": "INFO",
        "logPath" : "./logs",
        "staticPath" : "./static"
    },
    "database" : {
        "instances": [
            {
                "name": "default",
                "type": "sqlite",
                "database": "./db/default.db"
            },
            {
                "name": "mysql",
                "type": "mysql",
                "host": "localhost",
                "port": 3306,
                "database": "testdb",
                "parameters": "?useUnicode=true&characterEncoding=utf-8",
                "username": "root",
                "password": "root",
                "pool" : {
                    "initialSize": 5,
                    "maxActive": 50
                }
            }
        ],
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
    },
    "rest" : {
        "enable" : true,
        "listenOn": "localhost",
        "port": 11215
    },
    "tile" : {
        "enable"   : false,
        "logLevel" : "ERROR",
        "listenOn": "localhost",
        "port": 11214,
        "instances": [
            {
                "name": "tiles",
                "uri": "template+file://path/to/tiles?filetype=png",
                "cache" : "redis://?"
            },
            {
                "name": "arc-tiles",
                "uri": "arcgis://path/to/arcgis-tiles/Layers",
                "cache" : "memcached://?"
            }
        ]
    }
}
```

### 配置项说明

日志级别： "ERROR", "WARN", "INFO", "DEBUG"

根路径： 配置中相对路径的根路径为运行参数中maptalks.json所在目录

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>Module</th>
      <th>Setting</th>
      <th>
        <span class="option">Options</span> and <span class="flag">Flags</span>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr class="setting">
      <td rowspan="5">
        <p class="name"><strong>Server</strong></p>
        <p class="description"><strong>主服务</strong></p>
      </td>
      <td>
        <p class="name"><strong>端口</strong></p>
        <p class="description">主服务端口</p>
      </td>
      <td class="align-center">
        <p><code class="option">"port" ： NUMBER</code></p>
        <p class="description">默认 : 8090</p>
      </td>
    </tr>
    <tr class="setting">
      <td>
        <p class="name"><strong>监听地址</strong></p>
        <p class="description">主服务的监听地址， 即只响应指定地址的网络请求</p>
      </td>
      <td class="align-center">
        <p><code class="option">"listenOn" ： "0.0.0.0"</code></p>
        <p class="description">默认 : "0.0.0.0"，即不做限制</p>
      </td>
    </tr>
    <tr class="setting">
      <td>
        <p class="name"><strong>日志级别</strong></p>
        <p class="description">主服务日志级别</p>
      </td>
      <td class="align-center">
        <p><code class="option">"logLevel" ： "INFO"</code></p>
        <p class="description">默认 : "INFO"</p>
      </td>
    </tr>
    <tr class="setting">
      <td>
        <p class="name"><strong>日志文件夹</strong></p>
        <p class="description">主服务日志的文件夹</p>
      </td>
      <td class="align-center">
        <p><code class="option">"logPath" ： "./logs"</code></p>
        <p class="description">默认 : "./logs"</p>
      </td>
    </tr>
    <tr class="setting">
      <td>
        <p class="name"><strong>静态资源文件夹</strong></p>
        <p class="description">静态资源文件夹路径</p>
      </td>
      <td class="align-center">
        <p><code class="option">"staticPath" ： "./static"</code></p>
        <p class="description">默认 : "./static"</p>
      </td>
    </tr>
    
  </tbody>
</table>
</div>