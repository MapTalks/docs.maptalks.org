---
layout: docs
title: RestFul接口 - 空间数据库
permalink: /docs-cn/rest-api-database/
---

# 空间数据库 #

输入数据编码格式（针对POST、PUT方法）: x-www-form-urlencoded

## 获取空间库信息 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>GET</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>N/A</td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {
                "success": true,
                "data": {
                    "version": 1.0,
                    "crs": {
                        "type": "proj4",
                        "properties": {
                            "proj": "+proj=longlat +datum=GCJ02"
                        }
                    }
                }
            }
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 安装配置空间库 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}?op=install</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>
            <p>
                <code>settings=[string]: 设置参数<code>
                <br>
                例如：
                <code>
                {
                    "crs": {
                        "type": "proj4",
                        "properties": {
                            "proj": "+proj=longlat +datum=GCJ02"
                        }
                    }
                }
                </code>
            </p>
        </td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 获取图层列表信息 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>GET</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>N/A</td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {
                "success": true,
                "count": 1,
                "data": [
                    {
                        "id": "id",
                        "name": "name",
                        "type": "db_table",
                        "source": "source",
                        "fields": [
                            {
                                "fieldName": "field name",
                                "fieldsize": 20,
                                "dataType": "VARCHAR",
                                "decimalSize": 0,
                                "notNull": 1
                            }
                        ]
                    }
                ]
            }
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 创建图层 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers?op=create</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>
            <p>
                <code>data=[string]: 图层参数<code>
                <br>
                例如：
                {
                    "id": "id",
                    "name": "name",
                    "type": "db_table",
                    "source": "source",
                    "fields": [
                        {
                            "fieldName": "field name",
                            "fieldsize": 20,
                            "dataType": "VARCHAR",
                            "decimalSize": 0,
                            "notNull": 1
                        }
                    ]
                }
                </code>
            </p>
        </td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 获取图层信息 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>GET</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>N/A</td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
                {
                    "success": true,
                    "count": 1,
                    "data": [
                        {
                            "id": "id",
                            "name": "name",
                            "type": "db_table",
                            "source": "source",
                            "fields": [
                                {
                                    "fieldName": "field name",
                                    "fieldsize": 20,
                                    "dataType": "VARCHAR",
                                    "decimalSize": 0,
                                    "notNull": 1
                                }
                            ]
                        }
                    ]
                }
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 更新图层 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}?op=update</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
       </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>
            <p>
                <code>data=[string]: 图层参数<code>
                <br>
                例如：
                {
                    "id": "id",
                    "name": "name",
                    "type": "db_table",
                    "source": "source",
                    "fields": [
                        {
                            "fieldName": "field name",
                            "fieldsize": 20,
                            "dataType": "VARCHAR",
                            "decimalSize": 0,
                            "notNull": 1
                        }
                    ]
                }
                </code>
            </p>
        </td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 删除图层 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}?op=remove</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>N/A</td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 获取图层字段列表信息 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}/fields</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>GET</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>N/A</td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {
                "success": true,
                "count": 1,
                "data": [
                    {
                        "fieldName": "field name",
                        "fieldsize": 0,
                        "dataType": "INT",
                        "decimalSize": 8,
                        "notNull": 1
                    }
                ]
            }
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 创建图层字段 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}/fields?op=create</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>
            <p>
                <code>data=[string]: 图层字段参数<code>
                <br>
                例如：
                {
                    "fieldName": "field name",
                    "fieldsize": 20,
                    "dataType": "VARCHAR",
                    "decimalSize": 0,
                    "notNull": 1
                }
                </code>
            </p>
        </td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 更新图层字段 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}/fields/{field}?op=update</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
            <p>
                <code>field=[string]: 字段名</code>
                <br>
                例如：field1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>
            <p>
                <code>data=[string]: 图层字段参数<code>
                <br>
                例如：
                {
                    "fieldName": "field1",
                    "fieldsize": 50,
                    "dataType": "VARCHAR",
                    "decimalSize": 0,
                    "notNull": 0
                }
                </code>
            </p>
        </td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 删除图层字段 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}/fields?op=remove</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
            <p>
                <code>field=[string]: 字段名</code>
                <br>
                例如：field1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>N/A</td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 增加图层数据 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}/data?op=create</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>
            <p>
                <code>crs=[json]: 数据的CRS</code>
                <br>
                例如：
                <code>
                {
                    "type": "proj4",
                    "properties": {
                        "proj": "+proj=longlat +datum=GCJ02"
                    }
                }
                </code>
            </p>
            <p>
                <code>data=[json|json array]: 数据的JSON表达</code>
                <br>
                例如：
                <code>
                {
                    "type": "Feature",
                    "geometry": {
                        "type": "Polygon",
                        "coordinates": [[
                            [-10.0, -10.0], [10.0, -10.0], [10.0, 10.0], [-10.0, 10.0]
                        ]]
                    }
                }
                </code>
            </p>
        </td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 查询图层数据 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}/data?op=query</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>
            <p>
                <code>condition=[string]: 查询条件</code>
                <br>
                例如：prop1='hello'
            </p>
            <p>
                <code>spatialFilter=[json]: 空间过滤条件</code>
                <br>
                例如：
                <code>
                {
                    // RELATION_WITHIN
                    relation: 5,
                    geometry: {
                        type: 'Polygon',
                        coordinates: [
                            [ [-120.0, 84.0], [120.0, 84.0], [120.0, -84.0], [-120.0, -84.0], [-120.0, 84.0] ]
                        ]
                    }
                }
                </code>
            </p>
            <p>
                <code>fields=[string]: 返回字段列表</code>
                <br>
                例如：prop1,prop2
            </p>
            <p>
                <code>returnGeometry=[bool]: 是否返回Geometry，默认true</code>
                <br>
                例如：false
            </p>
            <p>
                <code>resultCRS=[string|json]: 返回数据的CRS</code>
                <br>
                例如：
                <code>
                {
                    "type": "proj4",
                    "properties": {
                        "proj": "+proj=longlat +datum=BD09"
                    }
                }
                </code>
                <br>
                或者：
                <code>
                BD09
                </code>
            </p>
            <p>
                <code>page=[int]: 页编号，从0开始</code>
            </p>
            <p>
                <code>count=[int]: 每页数量</code>
            </p>
        </td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {
                "success": true,
                "data": [
                    {
                        "type": "Feature",
                        "id": "fid",
                        "geometry": {
                            "type": "Polygon",
                            "coordinates": [[
                                [-10.0, -10.0], [10.0, -10.0], [10.0, 10.0], [-10.0, 10.0]
                            ]]
                        }
                    }
                ]
            }
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 查询图层数据数量 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}/data?op=count</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>
            <p>
                <code>condition=[string]: 查询条件</code>
                <br>
                例如：prop1='hello'
            </p>
            <p>
                <code>spatialFilter=[json]: 空间过滤条件</code>
                <br>
                例如：
                <code>
                {
                    // RELATION_WITHIN
                    relation: 5,
                    geometry: {
                        type: 'Polygon',
                        coordinates: [
                            [ [-120.0, 84.0], [120.0, 84.0], [120.0, -84.0], [-120.0, -84.0], [-120.0, 84.0] ]
                        ]
                    }
                }
                </code>
            </p>
            <p>
                <code>fields=[string]: 返回字段列表</code>
                <br>
                例如：prop1,prop2
            </p>
            <p>
                <code>returnGeometry=[bool]: 是否返回Geometry，默认true</code>
                <br>
                例如：false
            </p>
            <p>
                <code>resultCRS=[string|json]: 返回数据的CRS</code>
                <br>
                例如：
                <code>
                {
                    "type": "proj4",
                    "properties": {
                        "proj": "+proj=longlat +datum=BD09"
                    }
                }
                </code>
                <br>
                或者：
                <code>
                BD09
                </code>
            </p>
        </td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {
                "success": true,
                "count": 0,
                "data": 145
            }
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 删除图层数据 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}/data?op=remove</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>
            <p>
                <code>condition=[string]: 查询条件</code>
                <br>
                例如：id='fid'
            </p>
        </td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 删除所有图层数据 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}/data?op=removeAll</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>N/A</td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 更新图层数据 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}/data?op=update</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>
            <p>
                <code>crs=[json]: 数据的CRS</code>
                <br>
                例如：
                <code>
                {
                    "type": "proj4",
                    "properties": {
                        "proj": "+proj=longlat +datum=GCJ02"
                    }
                }
                </code>
            </p>
            <p>
                <code>condition=[string]: 查询条件</code>
                <br>
                例如：id='fid'
            </p>
            <p>
                <code>data=[json]: 数据的JSON表达</code>
                <br>
                例如：
                <code>
                {
                    "type": "Feature",
                    "id": "fid",
                    "geometry": {
                        "type": "Polygon",
                        "coordinates": [[
                            [-10.0, -10.0], [10.0, -10.0], [10.0, 10.0], [-10.0, 10.0]
                        ]]
                    }
                }
                </code>
            </p>
        </td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>

## 更新图层数据属性 ##
<div>
<table><tbody>
    <tr>
        <td>URL</td>
        <td>/rest/sdb/databases/{db}/layers/{layerid}/data?op=updateProperties</td>
    </tr>
    <tr>
        <td>请求方法</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>路径参数</td>
        <td>
            <p>
                <code>db=[string]: 数据库名字</code>
                <br>
                例如：db1
            </p>
            <p>
                <code>layerid=[string]: 图层ID</code>
                <br>
                例如：layer1
            </p>
        </td>
    </tr>
    <tr>
        <td>数据参数</td>
        <td>
            <p>
                <code>condition=[string]: 查询条件</code>
                <br>
                例如：id='fid'
            </p>
            <p>
                <code>data=[json]: 新的属性</code>
                <br>
                例如：
                <code>
                {
                    "prop1": "new string",
                    "prop2": 99
                }
                </code>
            </p>
        </td>
    </tr>
    <tr>
        <td>请求成功的回应</td>
        <td>
            <code>
            {"success": true}
            </code>
        </td>
    </tr>
    <tr>
        <td>请求失败的回应</td>
        <td>
            <code>
            {"success": false}
            </code>
        </td>
    </tr>
</tbody></table>
</div>
