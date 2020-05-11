### fluentlogger简单易用的日志收集器

[历史源码位置](https://github.com/kasiss-liu/go-tools/tree/master/fluent-logger)

#### Features
- 能够进行简单的日志格式化和日志收集
- 无/小时/天 三种日志分割模式可选


#### Usage
```shell
go get -u github.com/kasiss-liu/go-fluentlogger
```

```go
logger.RegisterFileLogger("test", "./test", "testlogger", PartitionNone)
err := logger.StartLogger()
if err != nil {
    fmt.Println(err.Error())
}

tm := time.Now()
logger.Log("test", fmt.Sprintf("%s%s", "testlog_", "log"), tm)
logger.Notice("test", fmt.Sprintf("%s%s", "testlog_", "notice"), tm)
logger.Warning("test", fmt.Sprintf("%s%s", "testlog_", "warning"), tm)
logger.Error("test", fmt.Sprintf("%s%s", "testlog_", "error"), tm)

```