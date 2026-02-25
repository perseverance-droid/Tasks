# 二、Go 学习笔记

## 1.Go 初识

- go run main.go ：编译+直接运行，不生成文件，写代码时测试

- go build main.go ：编译成可执行文件

## 2.环境搭建

- 在 Linux 虚拟机里装 Go： sudo apt install golang 

- VS Code 用 Remote-SSH 连虚拟机，选 NAT 模式，拿到 IP 就能连

## 3.基础语法

- 每个Go文件第一行必须是  package main ，不然运行不了

> 我一开始忘写，报错“cannot run non-main package”

- 用  import "fmt"  导入输入输出包，才能在终端打印东西、读用户输入。

- 程序入口是  func main() ，所有代码都写在这个函数里。

- 变量：我用  var name string  定义名字，或者  age := 18  简写

- 输出： fmt.Println("Hello")  换行打印， fmt.Printf("你好%s", name)  格式化输出。

- 输入： fmt.Scan(&name)  从终端读用户输入，注意要加  &  取地址

> 我一开始漏了，程序读不到输入。

 