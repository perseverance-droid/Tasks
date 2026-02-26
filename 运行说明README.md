# 运行说明README

### 项目说明

本项目为Go语言网络基础demo，包含TCP通信Demo和HTTP通信Demo两部分

### 文件清单

1.  tcp_server.go  —— TCP服务端
2.  tcp_client.go  —— TCP客户端
3.  http_server.go  —— HTTP服务端
4.  http_client.go  —— HTTP客户端

 

## 一、TCP Demo 运行步骤

1. 启动服务端

打开第一个终端，输入命令：

```plaintext
go run tcp_server.go
```

**启动成功提示：TCP服务端已启动，等待客户端连接...**

2. 启动客户端

打开第二个终端，输入命令：

```
go run tcp_client.go
```

**按提示输入消息，回车发送，即可看到服务端响应。**<br>

## 二、HTTP Demo 运行步骤

1. 启动HTTP服务端

打开第一个终端，输入命令：

```
go run http_server.go
```

**启动成功提示：HTTP服务端已启动，访问地址：http://127.0.0.1:9090/hello**

2. 启动HTTP客户端

打开第二个终端，输入命令：

```
go run http_client.go
```

**运行后会打印服务端返回的**状态码（200）**和响应内容。**

> TCP Demo：两端能正常收发消息，无报错

> HTTP Demo：客户端打印状态码200，服务端打印请求信息

