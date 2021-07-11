## golang 学习笔记



### 语法

### 数据结构

### 并发

### web开发

#### 启动web服务

1. 编写handler函数
2. 编写main方法
3. 注册handler函数
4. 启动服务

```go
package main

import (
	"fmt"
	"log"
	"net/http"
)

func handler(w http.ResponseWriter, r *http.Request) {
	fmt.Fprintf(w, "Hi there, I love %s!", r.URL.Path[1:])
}

func main() {
	http.HandleFunc("/", handler)
	log.Fatal(http.ListenAndServe(":8080", nil))
}

```

核心function

- HandleFunc
- ListenAndServe

