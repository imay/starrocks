# ST_Contains

## 功能

判断几何图形 `shape1` 是否完全能够包含几何图形 `shape2`。

## 语法

```Haskell
ST_Contains(shape1, shape2)
```

## 参数说明

`shape1`: 几何图形 1，包含图形，支持的数据类型为 GEOMETRY。

`shape2`: 几何图形 2，被包含图形，支持的数据类型为 GEOMETRY。

## 返回值说明

返回值的数据类型为 BOOLEAN。

## 示例

```Plain Text
MySQL > SELECT ST_Contains(ST_Polygon("POLYGON ((0 0, 10 0, 10 10, 0 10, 0 0))"), ST_Point(5, 5));
+----------------------------------------------------------------------------------------+
| st_contains(st_polygon('POLYGON ((0 0, 10 0, 10 10, 0 10, 0 0))'), st_point(5.0, 5.0)) |
+----------------------------------------------------------------------------------------+
|                                                                                      1 |
+----------------------------------------------------------------------------------------+

MySQL > SELECT ST_Contains(ST_Polygon("POLYGON ((0 0, 10 0, 10 10, 0 10, 0 0))"), ST_Point(50, 50));
+------------------------------------------------------------------------------------------+
| st_contains(st_polygon('POLYGON ((0 0, 10 0, 10 10, 0 10, 0 0))'), st_point(50.0, 50.0)) |
+------------------------------------------------------------------------------------------+
|                                                                                        0 |
+------------------------------------------------------------------------------------------+
```