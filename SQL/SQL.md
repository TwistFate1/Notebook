# SQL

> SQL（Structured Query Language）是一种用于管理和操作关系数据库的标准语言，包括数据查询、数据插入、数据更新、数据删除、数据库结构创建和修改等功能。

## 基本语法

### SELECT

> SELECT 语句用于从数据库中选取数据。

### DISTINCT

> DISTINCT 语句用于返回唯一不同的值。

### WHERE

> WHERE 子句用于过滤记录。

### AND & OR

> AND & OR 运算符用于基于一个以上的条件对记录进行过滤。

### ORDER BY

> ORDER BY 关键字用于对结果集进行排序。

### INSERT INTO

> INSERT INTO 语句用于向表中插入新记录。

### UPDATE

> UPDATE 语句用于更新表中的记录。

### DELETE

> DELETE 语句用于删除表中的记录。

## 高级语法

### SELECT TOP, LIMIT

> SELECT TOP, LIMIT 语句用于在 SQL 中限制返回的结果集中的行数。

### LIKE

> LIKE 操作符用于在 WHERE 子句中搜索列中的指定模式。

### 通配符

| 通配符 | 描述 |
| :-: | :-: |
| % | 替代 0 个或多个字符 |
| _ | 替代一个字符 |
| [charlist] | 字符列中的任何单一字符 |
| [^charlist] 或 [!charlist] | 不在字符列中的任何单一字符 |

### IN

> IN 操作符允许您在 WHERE 子句中规定多个值。

### BETWEEN

> BETWEEN 操作符选取介于两个值之间的数据范围内的值，这些值可以是数值、文本或者日期。

### AS

> AS 为表名称或列名称指定别名。

### JOIN

> 使用 ON 关键字指定连接条件。

#### INNER JOIN

> 交集。

#### LEFT JOIN

> 从左表返回所有的行，即使右表中没有匹配。如果右表中没有匹配，则结果为 NULL。

#### RIGHT JOIN

> 从右表返回所有的行，即使左表中没有匹配。如果左表中没有匹配，则结果为 NULL。

#### FULL JOIN

> 同时保留两个表所有的行。如果其中一方没有匹配，则结果为NULL。

### UNION

> UNION 操作符合并两个或多个 SELECT 语句的结果。

### SELECT INTO

> 将一个表的信息复制到另一个表。

### INSERT INTO SELECT

> 将一个表 SELECT 的行插入另一个表。

### CREATE DATABASE

> CREATE DATABASE 语句用于创建数据库。

### CREATE TABLE

> CREATE TABLE 语句用于创建数据库中的表。

### 约束

#### NOT NULL

> 指示某列不能存储 NULL 值。

#### UNIQUE

> 保证某列的每行必须有唯一的值。

#### PRIMARY KEY

> 确保某列（或两个以上列的结合）有唯一标识，有助于更容易更快速地找到表中的一个特定的记录。

#### FOREIGN KEY

> 保证一个表中的数据匹配另一个表中的值的参照完整性。

#### CHECK

> 保证列中的值符合指定的条件。

#### DEFAULT

> 规定没有给列赋值时的默认值。

#### INDEX

> 用于快速访问数据库表中的数据。

### DROP

> 丢弃。

### ALTER

> 调整。

### AUTO INCREMENT

> 自增。

### VIEW

> 视图是可视化的表。

## SQL 函数

### SQL Aggregate 函数

#### AVG 函数

> AVG 函数返回数值列的平均值。

#### COUNT

> COUNT 函数返回匹配指定条件的行数。

#### FIRST

> FIRST 函数返回指定的列中第一个记录的值。

#### LAST

> LAST 函数返回指定的列中最后一个记录的值。

#### MAX

> MAX 函数返回指定列的最大值。

#### MIN

> MIN 函数返回指定列的最小值。

#### SUM

> SUM 函数返回数值列的总数。

#### GROUP BY

> GROUP BY 对结果集进行分组。

#### HAVING

> HAVING 子句可以让我们筛选分组后的各组数据（聚合函数无法与 WHERE 结合使用）。

#### EXISTS

> EXISTS 运算符用于判断查询子句是否有记录。

### SQL Scalar 函数

#### UCASE

> UCASE 函数把字段的值转换为大写。

#### LCASE

> LCASE 函数把字段的值转换为小写。

#### MID

> MID 函数用于从文本字段中提取字符。

#### LEN

> LEN 函数返回文本字段中值的长度。

#### ROUND

> ROUND 函数用于把数值字段舍入为指定的小数位数。

#### NOW

> NOW 函数返回当前系统的日期和时间。

#### FORMAT

> FORMAT 函数用于对字段的显示进行格式化。
