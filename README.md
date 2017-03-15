log
==============
log is a simple and useful logging tool of Go. see [API](https://godoc.org/github.com/imroc/log).

## Features
 * light weight
 * easy to use

## Note
there is only 2 log level(Debug,Info) the philosophy of this can be found in [here](https://dave.cheney.net/2015/11/05/lets-talk-about-logging)

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
	log.Debug("debug ", "message")
	log.Infof("%s message", "info")
}
```
output:
``` 
2016/10/04 14:38:38 [DEBG] main.go:7 debug message
2016/10/04 14:38:38 [INFO] main.go:8 info message
```
##### More Control
``` go
log.SetFilename("test.log")
log.SetFlag(log.Ldate | log.Ltime | log.Llongfile)
log.SetDebug(false)
```
## LICENSE
log is is distributed under the terms of the MIT License.
