# Gorm 学习笔记

## 1.Gorm 是什么

Gorm 是 Go 语言最流行的 ORM（对象关系映射）框架，作用是用 Go 结构体操作数据库，**不用手写复杂 SQL，代码更简洁、更安全**。

## 2.安装与连接

- 安装

```bash
go get -u gorm.io/gorm
go get -u gorm.io/driver/mysql
```

- 连接数据库

```go
package main

import (
  "gorm.io/driver/mysql"
  "gorm.io/gorm"
)

func main() {
  dsn := "root:123456@tcp(127.0.0.1:3306)/testdb?charset=utf8mb4&parseTime=True&loc=Local"
  db, err := gorm.Open(mysql.Open(dsn), &gorm.Config{})
  if err != nil {
    panic("连接数据库失败")
  }
}
```



## 3.基础 CRUD 操作

- 新增


```go
user := User{Username: "lisi", Password: "123", Age: 20}
db.Create(&user)
```

- 查询


```go
var u User
db.First(&u, 1) // 根据 ID 查询

var list []User
db.Where("age > ?", 18).Find(&list) // 条件查询
```

- 修改


```go
db.Model(&u).Update("age", 22) // 更新单个字段
db.Model(&u).Updates(User{Username: "wangwu", Age: 23}) // 更新多个字段
```

- 删除


```go
db.Delete(&u, 1) // 软删除
db.Unscoped().Delete(&u) // 硬删除
```

> 硬删除就是真的删了，数据库里直接没了。
>
> 软删除不是真删，只是标记“已删除”，数据还在库里。

## 4.高级查询

- 排序

```go
db.Order("age desc").Find(&list)
```

- 分页

```go
db.Limit(10).Offset(20).Find(&list)
```

 