# Feb 18-24 \[concurrency and qps\]

## Tip & Sharing

### qps and response time

qps: query per second, 每秒请求数。response time: 单个请求的响应时间。

单线程场景下，qps = 1/ rt

多线程场景下，qps = n\*1/rt

以上两个指标常用来衡量应用性能。但是即使是同一个api的请求，它可能hit db，也可能hit cache，两者需要的资源和响应时间必定不同，因此这两个数据未必能准确衡量应用的性能。

### **parallelism**

并行：同一时刻有超过一个task在执行。

最简单的例子是多线程/进程。单线程无法达到并行状态。

### **concurrency**

通常所说的并发，指的是程序结构/设计支持并发请求。

正确的并发设计的标准是：使多个操作可以在重叠的时间段内进行\(two tasks can start, run, and complete in overlapping time periods\)。除了上文所说的并行，协程\(coroutine\)也是一种并发。

![&#x534F;&#x7A0B;](../.gitbook/assets/image%20%285%29.png)

关于并发和并行，可以参考这篇博客：

{% embed url="https://laike9m.com/blog/huan-zai-yi-huo-bing-fa-he-bing-xing,61/" %}

