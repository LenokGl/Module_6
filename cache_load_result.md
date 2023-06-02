without cache
lenok@WIN-2IDRRNTM3EJ:~$ wrk -d 60 -t 1  -c 1 --latency -s ./get.lua http://localhost:8081/
Running 1m test @ http://localhost:8081/
  1 threads and 1 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    23.12ms   59.28ms 771.50ms   94.70%
    Req/Sec   103.78     59.49   250.00     60.87%
  Latency Distribution
     50%    7.70ms
     75%   17.40ms
     90%   37.51ms
     99%  311.51ms
  5879 requests in 1.00m, 0.86MB read
  Non-2xx or 3xx responses: 5879
Requests/sec:     97.90
Transfer/sec:     14.72KB

with cache
lenok@WIN-2IDRRNTM3EJ:~$ wrk -d 60 -t 1  -c 1 --latency -s ./get.lua http://localhost:8082/
Running 1m test @ http://localhost:8082/
  1 threads and 1 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    36.39ms   98.09ms 823.38ms   93.01%
    Req/Sec    96.53     58.53   252.00     63.18%
  Latency Distribution
     50%    6.96ms
     75%   16.80ms
     90%   62.08ms
     99%  551.00ms
  3004 requests in 1.01m, 451.77KB read
  Socket errors: connect 0, read 0, write 0, timeout 2
  Non-2xx or 3xx responses: 3004
Requests/sec:     49.40
Transfer/sec:      7.43KB


without cache
Running 1m test @ http://localhost:8081/
  10 threads and 10 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   126.24ms  234.79ms   1.76s    90.57%
    Req/Sec    21.57     13.18    60.00     67.48%
  Latency Distribution
     50%   43.32ms
     75%   85.25ms
     90%  343.01ms
     99%    1.27s
  8197 requests in 1.00m, 1.20MB read
  Socket errors: connect 0, read 3, write 0, timeout 30
  Non-2xx or 3xx responses: 8197
Requests/sec:    136.47
Transfer/sec:     20.52KB

with cache
Running 1m test @ http://localhost:8082/
  10 threads and 10 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    44.21ms   28.95ms 250.46ms   84.83%
    Req/Sec    24.69     10.09    70.00     71.51%
  Latency Distribution
     50%   37.80ms
     75%   52.24ms
     90%   72.18ms
     99%  162.84ms
  14603 requests in 1.00m, 2.14MB read
  Non-2xx or 3xx responses: 14603
Requests/sec:    243.11
Transfer/sec:     36.56KB

without cache
Running 1m test @ http://localhost:8081/
  50 threads and 50 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   188.00ms  132.19ms   1.17s    85.24%
    Req/Sec     6.88      4.03    29.00     86.19%
  Latency Distribution
     50%  155.05ms
     75%  223.48ms
     90%  327.36ms
     99%  707.18ms
  16040 requests in 1.00m, 2.36MB read
  Socket errors: connect 0, read 0, write 0, timeout 100
  Non-2xx or 3xx responses: 16040
Requests/sec:    266.41
Transfer/sec:     40.07KB

with cache
Running 1m test @ http://localhost:8082/
  50 threads and 50 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   172.27ms  116.02ms 846.16ms   85.34%
    Req/Sec     7.50      3.95    30.00     84.17%
  Latency Distribution
     50%  139.89ms
     75%  198.16ms
     90%  304.86ms
     99%  623.69ms
  19082 requests in 1.00m, 2.80MB read
  Non-2xx or 3xx responses: 19082
Requests/sec:    317.32
Transfer/sec:     47.72KB