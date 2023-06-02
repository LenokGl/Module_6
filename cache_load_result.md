<p> without cache </p>
lenok@WIN-2IDRRNTM3EJ:~$ wrk -d 60 -t 1  -c 1 --latency -s ./get.lua http://localhost:8081/
Running 1m test @ http://localhost:8081/<br>
  1 threads and 1 connections <br> 
  Thread Stats   Avg      Stdev     Max   +/- Stdev <br>
    Latency    23.12ms   59.28ms 771.50ms   94.70% <br>
    Req/Sec   103.78     59.49   250.00     60.87% <br>
  Latency Distribution <br>
     50%    7.70ms <br>
     75%   17.40ms <br>
     90%   37.51ms <br>
     99%  311.51ms <br>
  5879 requests in 1.00m, 0.86MB read <br>
  Non-2xx or 3xx responses: 5879 <br>
Requests/sec:     97.90 <br>
Transfer/sec:     14.72KB <br>

<p> with cache </p>
lenok@WIN-2IDRRNTM3EJ:~$ wrk -d 60 -t 1  -c 1 --latency -s ./get.lua http://localhost:8082/
Running 1m test @ http://localhost:8082/ <br>
  1 threads and 1 connections <br>
  Thread Stats   Avg      Stdev     Max   +/- Stdev <br>
    Latency    36.39ms   98.09ms 823.38ms   93.01% <br>
    Req/Sec    96.53     58.53   252.00     63.18% <br>
  Latency Distribution <br>
     50%    6.96ms <br>
     75%   16.80ms <br>
     90%   62.08ms <br>
     99%  551.00ms <br>
  3004 requests in 1.01m, 451.77KB read <br>
  Socket errors: connect 0, read 0, write 0, timeout 2 <br>
  Non-2xx or 3xx responses: 3004 <br>
Requests/sec:     49.40 <br>
Transfer/sec:      7.43KB <br>


<p> without cache </p>
Running 1m test @ http://localhost:8081/
  10 threads and 10 connections <br>
  Thread Stats   Avg      Stdev     Max   +/- Stdev <br>
    Latency   126.24ms  234.79ms   1.76s    90.57% <br>
    Req/Sec    21.57     13.18    60.00     67.48% <br>
  Latency Distribution <br>
     50%   43.32ms <br>
     75%   85.25ms <br>
     90%  343.01ms <br>
     99%    1.27s <br>
  8197 requests in 1.00m, 1.20MB read <br>
  Socket errors: connect 0, read 3, write 0, timeout 30 <br>
  Non-2xx or 3xx responses: 8197 <br>
Requests/sec:    136.47 <br>
Transfer/sec:     20.52KB <br>

<p> with cache </p>
Running 1m test @ http://localhost:8082/
  10 threads and 10 connections <br>
  Thread Stats   Avg      Stdev     Max   +/- Stdev <br>
    Latency    44.21ms   28.95ms 250.46ms   84.83% <br>
    Req/Sec    24.69     10.09    70.00     71.51% <br>
  Latency Distribution <br>
     50%   37.80ms <br> 
     75%   52.24ms <br>
     90%   72.18ms <br>
     99%  162.84ms <br>
  14603 requests in 1.00m, 2.14MB read <br>
  Non-2xx or 3xx responses: 14603 <br>
Requests/sec:    243.11 <br>
Transfer/sec:     36.56KB <br>

<p> without cache </p>
Running 1m test @ http://localhost:8081/
  50 threads and 50 connections <br> 
  Thread Stats   Avg      Stdev     Max   +/- Stdev <br> 
    Latency   188.00ms  132.19ms   1.17s    85.24% <br> 
    Req/Sec     6.88      4.03    29.00     86.19% <br> 
  Latency Distribution <br> 
     50%  155.05ms <br> 
     75%  223.48ms <br> 
     90%  327.36ms <br> 
     99%  707.18ms <br> 
  16040 requests in 1.00m, 2.36MB read <br> 
  Socket errors: connect 0, read 0, write 0, timeout 100
  Non-2xx or 3xx responses: 16040 <br> 
Requests/sec:    266.41 <br> 
Transfer/sec:     40.07KB <br> 

<p> with cache </p>
Running 1m test @ http://localhost:8082/
  50 threads and 50 connections <br> 
  Thread Stats   Avg      Stdev     Max   +/- Stdev <br> 
    Latency   172.27ms  116.02ms 846.16ms   85.34% <br> 
    Req/Sec     7.50      3.95    30.00     84.17% <br> 
  Latency Distribution <br> 
     50%  139.89ms <br> 
     75%  198.16ms <br> 
     90%  304.86ms <br> 
     99%  623.69ms <br> 
  19082 requests in 1.00m, 2.80MB read <br> 
  Non-2xx or 3xx responses: 19082 <br> 
Requests/sec:    317.32 <br> 
Transfer/sec:     47.72KB <br> 