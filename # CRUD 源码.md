# CRUD 源码

```go
package main

import (
  "fmt"
  "gorm.io/driver/mysql"
  "gorm.io/gorm"
)

// 定义 User 模型
type User struct {
  gorm.Model
  Username string
  Password string
  Age      int
}

func main() {
  // 1. 连接数据库
  dsn := "root:123456@tcp(127.0.0.1:3306)/testdb?charset=utf8mb4&parseTime=True&loc=Local"
  db, err := gorm.Open(mysql.Open(dsn), &gorm.Config{})
  if err != nil {
    panic("连接数据库失败: " + err.Error())
  }

  // 2. 自动创建表
  db.AutoMigrate(&User{})

  // 3. 新增数据
  user := User{Username: "testuser", Password: "123456", Age: 20}
  db.Create(&user)
  fmt.Println("新增用户 ID:", user.ID)

  // 4. 查询数据
  var u User
  db.First(&u, user.ID)
  fmt.Println("查询到用户:", u)

  // 5. 修改数据
  db.Model(&u).Update("age", 21)
  fmt.Println("修改后年龄:", u.Age)

  // 6. 删除数据
  db.Delete(&u)
  fmt.Println("删除成功")
}

 
```

