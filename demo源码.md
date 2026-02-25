# demo源码

```go
package main

import "fmt"

func main() {
	var name string
	fmt.Println("=== Go 控制台 Demo ===")
	fmt.Print("输入名字：")
	fmt.Scan(&name)
	fmt.Printf("你好，%s！\n", name)
```

