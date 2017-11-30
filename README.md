## Cloudgo-data：数据服务构建
### 1、使用 xorm 或 gorm 实现本文的程序，从编程效率、程序结构、服务性能等角度对比 database/sql 与 orm 实现的异同！
1. orm 是否就是实现了 dao 的自动化？
2. 使用 ab 测试性能
### 2、参考 Java JdbcTemplate 的设计思想，设计 GoSqlTemplate 的原型, 使得 sql 操作对于爱写 sql 的程序猿操作数据库更容易。
1. 轻量级别的扩展，程序员的最爱
2. 程序猿不怕写 sql ，怕的是线程安全处理和错误处理
3. sql 的 CRUD 操作 database/sql 具有强烈的模板特征，适当的回调可以让程序员自己编写 sql 语句和处理 RowMapping
4. 建立在本文 SQLExecer 接口之上做包装，直观上是有利的选择
5. 暂时不用考虑占位符等数据库移植问题，方便使用 mysql 或 sqlite3 就可以
### 安装

```javascript
   go get github.com/astaxie/beego/orm
```

### 测试部分

```javascript
   This is ApacheBench, Version 2.3 <$Revision: 1757674 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient)
Completed 100 requests
Completed 200 requests
Completed 300 requests
Completed 400 requests
Completed 500 requests
Completed 600 requests
Completed 700 requests
Completed 800 requests
Completed 900 requests
Completed 1000 requests
Finished 1000 requests


Server Software:        
Server Hostname:        localhost
Server Port:            8080

Document Path:          /service/userinfo?userid=
Document Length:        663 bytes

Concurrency Level:      100
Time taken for tests:   0.412 seconds
Complete requests:      1000
Failed requests:        0
Total transferred:      683000 bytes
HTML transferred:       559000 bytes
Requests per second:    2956.25 [#/sec] (mean)
Time per request:       37.256 [ms] (mean)
Time per request:       0.422 [ms] (mean, across all concurrent requests)
Transfer rate:          1888.89 [Kbytes/sec] received

Connection Times (ms)
               min  mean[+/-sd] median   max
Connect:        0    1   0.9      0       5
Processing:     1   34  29.5     27     137
Waiting:        1   33  29.5     27     137
Total:          1   34  29.7     27     139
WARNING: The median and mean for the initial connection time are not within a normal deviation
        These results are probably not that reliable.

Percentage of the requests served within a certain time (ms)
50%     22
66%     34
75%     36
80%     42
90%     90
95%    117
98%    123
99%    134
100%    143 (longest request)
```
