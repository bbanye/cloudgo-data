##Cloudgo-data�����ݷ��񹹽�
###1��ʹ�� xorm �� gorm ʵ�ֱ��ĵĳ��򣬴ӱ��Ч�ʡ�����ṹ���������ܵȽǶȶԱ� database/sql �� orm ʵ�ֵ���ͬ��

 1.orm �Ƿ����ʵ���� dao ���Զ�����

 2.ʹ�� ab ��������
###2���ο� Java JdbcTemplate �����˼�룬��� GoSqlTemplate ��ԭ��, ʹ�� sql �������ڰ�д sql �ĳ���Գ�������ݿ�����ס�

 1.�����������չ������Ա���

 2.����Գ����д sql ���µ����̰߳�ȫ����ʹ�����

 3.sql �� CRUD ���� database/sql ����ǿ�ҵ�ģ���������ʵ��Ļص������ó���Ա�Լ���д sql ���ʹ��� RowMapping

 4.�����ڱ��� SQLExecer �ӿ�֮������װ��ֱ������������ѡ��

 5.��ʱ���ÿ���ռλ�������ݿ���ֲ���⣬����ʹ�� mysql �� sqlite3 �Ϳ���
###��װ

```javascript
   go get github.com/astaxie/beego/orm
```

###���Բ���

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