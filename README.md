log
==============
log is a logging framework of Go. see [API](https://godoc.org/github.com/imroc/log).

## Features
 * light weight
 * easy to use
 * level logging support
 * flexible

## Quick Start

##### Installation
``` sh
go get github.com/imroc/log
```
##### Simple Usage
``` go
import (
	"github.com/imroc/log"
)

func main() {
    // DEBUG < INFO < WARN < ERROR < FATAL
    log.SetLevel(log.WARN) // level DEBUG and INFO will not output
	log.Debug("this is a %s message", "debug")
	log.Info("this is a %s message", "info")
	log.Warn("this is a %s message", "warn")
	log.Error("this is a %s message", "error")
	log.Fatal("this is a %s message", "fatal")
}
```
output:
``` 
2016/10/04 14:38:38 WARN this is a warn message
2016/10/04 14:38:38 EROR this is a error message
2016/10/04 14:38:38 FATL this is a fatal message
```
##### More Control
``` go
file, _ := os.OpenFile("test.log", os.O_WRONLY|os.O_CREATE|os.O_APPEND, 0666)
log.Set(log.INFO, file, log.Llongfile|log.LstdFlags)
log.Debug("this is a %s message", "debug")
log.Info("this is a %s message", "info")
log.Warn("this is a %s message", "warn")
log.Error("this is a %s message", "error")
log.Fatal("this is a %s message", "fatal")
```
output to test.log:
```
2016/10/04 15:04:00 INFO /home/cpwl/go/lib/src/github.com/imroc/sub/test.go:13: this is a info message
2016/10/04 15:04:00 WARN /home/cpwl/go/lib/src/github.com/imroc/sub/test.go:14: this is a warn message
2016/10/04 15:04:00 EROR /home/cpwl/go/lib/src/github.com/imroc/sub/test.go:15: this is a error message
2016/10/04 15:04:00 FATL /home/cpwl/go/lib/src/github.com/imroc/sub/test.go:16: this is a fatal message
```
## LICENSE
log is is distributed under the terms of the MIT License.
