log
==============
log is a logging framework of Go. see [API](https://godoc.org/github.com/imroc/log).

## Features
 * light weight
 * easy to use

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
	log.DEBUG = true
	log.Debug("debug ", "message")
	log.Infof("%s message", "info")
	log.Fatal(errors.New("fatal message"))
}
```
output:
``` 
2016/10/04 14:38:38 [DEBG] debug message
2016/10/04 14:38:38 [INFO] info message
2016/10/04 14:38:38 [FATL] fatal message
```
##### More Control
``` go
file, _ := os.OpenFile("test.log", os.O_WRONLY|os.O_CREATE|os.O_APPEND, 0666)
log.OUT = file
log.FLAG = Ldate | Ltime | Llongfile
```
## LICENSE
log is is distributed under the terms of the MIT License.
