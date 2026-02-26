# Demo 源码

## 1.TCP 服务端tcp_server.go

```go
package main

import (
	"fmt"
	"net"
)

func main() {
	fmt.Println("服务端启动啦")
    li, _ := net.Listen("tcp", ":9090")
defer li.Close()
conn, _ := li.Accept()
defer conn.Close()

fmt.Println("客户端连上了")

msg := make([]byte, 1024)
conn.Read(msg)
fmt.Println("客户端说：", string(msg))

conn.Write([]byte("我收到啦"))
```



## 2.TCP 客户端tcp_client.go

```go
package main

import (
	"fmt"
	"net"
)

func main() {
	fmt.Println("客户端启动")
conn, _ := net.Dial("tcp", "127.0.0.1:9090")
defer conn.Close()

conn.Write([]byte("你好服务端"))

msg := make([]byte, 1024)
conn.Read(msg)
fmt.Println("服务端说：", string(msg))
```
 

## 3.HTTP 服务端 http_server.go

```go
package main

import (
	"fmt"
	"net/http"
)

func main() {
	http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
		fmt.Fprintf(w, "这是我的HTTP服务端")
	})
fmt.Println("HTTP服务启动，端口8888")
http.ListenAndServe(":8888", nil)
```
}

## 4.HTTP 客户端http_client.go

```go
package main

import (
	"fmt"
	"net/http"
)

func main() {
	resp, _ := http.Get("http://127.0.0.1:8888")
	defer resp.Body.Close()
fmt.Println("请求成功")
fmt.Println("状态码：", resp.StatusCode)
```
