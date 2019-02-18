# Feb 18-24 \[concurrency and qps\]

## Tip & Sharing

### qps and response time

qps: query per second, 每秒请求数。response time: 单个请求的响应时间。

单线程场景下，qps = 1/ rt

多线程场景下，qps = n\*1/rt

以上两个指标常用来衡量应用性能。但是即使是同一个api的请求，它可能hit db，也可能hit cache，两者需要的资源和响应时间必定不同，因此这两个数据未必能准确衡量应用的性能。

### **parallelism**

### **concurrency**

\*\*\*\*



