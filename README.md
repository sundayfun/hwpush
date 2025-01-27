# hwpush
华为push

![](https://img.shields.io/badge/build-passing-brightgreen.svg?maxAge=2592000)
[![Software License](http://img.shields.io/badge/license-MIT-brightgreen.svg)](LICENSE)
[![GoDoc](https://godoc.org/github.com/geek-go/hwpush?status.svg)](https://godoc.org/github.com/geek-go/hwpush)

由于官方没有推出Go版本的推送SDK，故自己实现了。支持：

- 按cid单推
- 按cid群推

全推不支持，官方接口没有提供全推。  


## 使用

安装：
``` bash
go get https://github.com/geek-go/hwpush
```

SDK 测试（使用前先打开`hwpush_test.go`配置appid等参数）：
``` bash
# 测试单推
go test -v  -run="^TestHwPush_SendByCid$" 

# 测试群推
go test -v  -run="^TestHwPush_SendByCids$" 
```

其它例子参照 `hwpush_test.go` 的调用。

> 测试用例里针对SDK进行了一些封装，大家可以参考快速实现。

## 文档参考

https://godoc.org/github.com/geek-go/hwpush

## 如何参与该项目

如果需要增加个推其它接口的实现，请参考`push_send`实现。规范：

- 每个接口对应一个文件
- 每个文件均包含接口请求结构体、接口响应结构体、接口调用的实现
- 增加测试用例
- 注意避免过度封装，以免使用者困惑
