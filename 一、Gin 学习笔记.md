# Gin 学习笔记

## 1.什么是 Gin

Gin 是 Go 语言的 Web 框架，用来快速写接口。

安装：

```go
go get -u github.com/gin-gonic/gin
```


最简单启动服务示例：

```go
package main

import "github.com/gin-gonic/gin"

func main() {
    r := gin.Default()
    r.GET("/", func(c *gin.Context) {
        c.String(200, "Hello Gin")
    })
    r.Run(":8080")
}
```



## 2.路由：网址对应功能

示例：

```go
r.GET("/hello", helloFunc)      // 查询
r.POST("/register", register)   // 注册
r.PUT("/user", update)          // 修改
r.DELETE("/user/:id", delete)   // 删除
```

## 3.路由分组

```go
// 管理员接口
admin := r.Group("/admin")
{
    admin.GET("/users", getList)
    admin.DELETE("/user/:id", del)
}

// 用户接口
user := r.Group("/user")
{
    user.PUT("/profile", update)
}
```

## 4.MVC 架构

- Model：定义表结构
- Controller：写逻辑
- Router：注册路由

示例 Model：

```go
type Member struct {
    ID       uint
    Username string
    Password string
}
```

## 5.什么是 Web 后端？

前端：你能看见的页面、按钮、输入框。
后端：藏在服务器里，负责接收请求、查数据库、返回结果。

用户登录流程：
前端 → 发账号密码 → 后端接收 → 查数据库 → 返回成功/失败

## 6.API 接口

API 就是前端和后端沟通的入口。

- GET 查询
- POST 新增
- PUT 修改
- DELETE 删除

## 7.身份校验

- Cookie：存在浏览器
- Session：存在服务器
- JWT：现在最常用，适合前后端分离