# 阶段九：Go+Gin+MySQL 成员管理系统 Nginx 部署文档



## 一、部署架构概述

生产环境采用网关+后端架构：
**用户请求 → Nginx（反向代理80端口）→ Gin 后端服务（8080端口）→ MySQL数据库**

> Nginx 作为统一入口，负责请求转发、日志记录和安全隔离，让后端服务不直接暴露公网，更稳定、更安全。



## 二、部署步骤

### 1.服务器环境准备

以Ubuntu系统为例，安装Nginx并设置开机自启：



```
sudo apt update
sudo apt install nginx -y
sudo systemctl enable nginx
```



### 2.项目上传与编译

将代码上传到服务器后，编译成Linux可执行文件：



```
CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o member-server main.go
```



### 3.Nginx 反向代理配置



```
sudo nano /etc/nginx/conf.d/member.conf
```

#### 写入配置：

```nginx
server {   

​      listen 80;    
       server_name 你的服务器IP;  



​      location / {        

​      proxy_pass http://127.0.0.1:8080;       

​      proxy_set_header Host $host;

​      proxy_set_header X-Real-IP 

$remote_addr;    

​      } 

} 
```

#### 生效配置



```
sudo nginx -t
sudo systemctl reload nginx
```



### 4.服务后台运行与防火墙



```
nohup ./member-server &
sudo ufw allow 80/tcp
```

## 三、部署测试（输入什么 → 输出什么）

### 1.注册接口

- 请求： POST http://服务器IP/register 
- 传入：



```json
{
    "username":"test",
    "password":"123456",
    "name":"测试",
    "phone":"13800138000",
    "email":"test@qq.com"
}
```




- 正确输出：



```json
{"msg":"注册成功"}
```

 

### 2.登录接口

- 请求： POST http://服务器IP/login 
- 传入：



```json
{
    "username":"test",
    "password":"123456"
}
```




- 正确输出：



```json
{"msg":"登录成功","role":"user"}
```

 

### 3.管理员查看用户列表

- 请求： GET http://服务器IP/admin/members 
- 正确输出：用户列表数组

 

### 4.管理员审核用户

- 请求： PUT http://服务器IP/admin/audit/1 
- 正确输出：



```json
{"msg":"审核成功"}
```

 

### 5.管理员删除用户

- 请求： DELETE http://服务器IP/admin/member/1 
- 正确输出：



```json
{"msg":"删除成功"}
```

 

### 6.用户修改个人信息

- 请求： PUT http://服务器IP/user/info 
- 请求头： username: test 
- 传入：



```json
{
    "name":"新名字",
    "phone":"13900139000",
    "email":"new@qq.com"
}
```




- 正确输出：



```json
{"msg":"修改成功"}
```

