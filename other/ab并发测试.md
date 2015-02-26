##安装
`sudo apt-get install apache2-utils`
##`GET`请求测试
运行`ab -n 100 -c 10 http://www.meetu.hk/`对 http://www.meetu.hk/ 进行100次请求，10个并发请求压力测试结果。
```
This is ApacheBench, Version 2.3 <$Revision: 1638069 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking www.meetu.hk (be patient).....done


Server Software:        
Server Hostname:        www.meetu.hk
Server Port:            80

Document Path:          /
Document Length:        80527 bytes

Concurrency Level:      10
//整个测试持续的时间
Time taken for tests:   5.850 seconds
Complete requests:      100
Failed requests:        99
   (Connect: 0, Receive: 0, Length: 99, Exceptions: 0)
Total transferred:      8086140 bytes
HTML transferred:       8025340 bytes

//平均每秒处理17个请求
Requests per second:    17.09 [#/sec] (mean)

//平均每个请求处理时间为585毫秒 注:这里将一次10个并发请求看成一个整体 
Time per request:       585.001 [ms] (mean)

//平均每个并发请求处理时间为58毫秒 
Time per request:       58.500 [ms] (mean, across all concurrent requests)
Transfer rate:          1349.85 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:       30   32   1.9     31      41
Processing:   315  519 169.0    474    1034
Waiting:      171  342 141.5    314     858
Total:        345  550 169.0    505    1066

Percentage of the requests served within a certain time (ms)
//在这100个请求中有50%在505毫秒内完成
  50%    505
//在这100个请求中有66%在560毫秒内完成
  66%    560
  75%    596
  80%    684
  90%    817
  95%   1007
  98%   1034
  99%   1066
 100%   1066 (longest request)
```
##`POST`请求测试
+ `-p` 指定post文件的位置
+ `-T` 选项指定post文件的编码方式，默认是明文，如果指定-T 'application/x-www-form-urlencoded'，则表示post文件使用urlencode
+ `vi abtxt` 写入：
```
data
```
+ `ab -c 10 -n 100 -p abtxt http://localhost/Yii/Yii2/advanced/frontend/web/index.php?r=test%2Ftest`



