# MySQL 学习笔记

## 1.MySQL 是什么

MySQL 是一款开源、免费、轻量、稳定的关系型数据库，是后端开发最常用的数据存储工具，用来长期保存用户信息、业务记录、配置等数据。

## 2.核心概念

- 数据库（Database）：一个“文件夹”，用来存放多张表。
- 数据表（Table）：类似 Excel 表格，存储同一类数据（如用户表、文章表）。
- 字段（列 Column）：表的竖列，代表数据的属性（如用户名、年龄、ID）。
- 记录（行 Row）：表的横排，一条完整的数据（如一个用户就是一行）。
- 主键（Primary Key）：每条数据的唯一标识，一般叫  id ，不能为空、不能重复。
- 一对多关系：一个用户可以发布多篇文章，通过用户 ID 关联两张表。

## 3.SQL 基础操作

### （1）创建数据库

```sql
CREATE DATABASE testdb;
```

### (2)创建表

```sql
CREATE TABLE user (
    id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(50) NOT NULL,
    age INT,
    create_time DATETIME
);
```



### (3)增数据

```sql
INSERT INTO user (username, password, age)
VALUES ('zhangsan', '123456', 20);
```



### (4)查询数据

```sql
//查询所有用户
SELECT * FROM user;
//条件查询
SELECT * FROM user WHERE age > 18;
//查询指定字段
SELECT username, age FROM user;
```



### (5)修改数据

```sql
UPDATE user SET age=21 WHERE id=1;
```

### (6)删除数据

```sql
DELETE FROM user WHERE id=1;
```

> 5.6均必须加 WHERE，否则全表被删除！