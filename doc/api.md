# 基本API

## `OpenFile`

```go
package main

import (
	"log/slog"
	"os"

	"github.com/syndtr/goleveldb/leveldb"
	"github.com/syndtr/goleveldb/leveldb/opt"
)

var db *leveldb.DB

func main() {
	// 如果db不存在, 会新建db目录
	var err error
	db, err = leveldb.OpenFile("db", &opt.Options{})
	if err != nil {
		slog.Error("open leveldb failed", "err", err.Error())
		os.Exit(1)
	}
}
```