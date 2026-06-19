## Load Testing and Performance Optimization

The Lambda function was initially configured with **128 MB** of memory.

Performance testing was performed using Postman Runner with:

* 10 Virtual Users
* 2 Minute Duration
* Ramp Up (30 Seconds) Profile

### Baseline Test (128 MB Memory)

![Baseline Test](images/postman-load-test-results-1.png)

Results:

* Total Requests: 1,578
* Requests / Second: 13.11
* Average Response Time: 550 ms
* P90 Response Time: 568 ms
* P95 Response Time: 612 ms
* P99 Response Time: 1,289 ms
* Error Rate: 0%

---

### Optimization Performed

AWS Lambda memory allocation was increased from **128 MB** to **1024 MB**.

Increasing Lambda memory also increases available CPU resources, enabling the function to process requests more efficiently.

---

### Optimized Test (1024 MB Memory)

![Optimized Test](images/postman-load-test-results-2.png)

Results:

* Total Requests: 2,720
* Requests / Second: 22.59
* Average Response Time: 316 ms
* P90 Response Time: 321 ms
* P95 Response Time: 328 ms
* P99 Response Time: 376 ms
* Error Rate: 0%

---

### Performance Comparison

| Metric            |   128 MB | 1024 MB | Improvement |
| ----------------- | -------: | ------: | ----------: |
| Total Requests    |    1,578 |   2,720 |        +72% |
| Requests / Second |    13.11 |   22.59 |        +72% |
| Avg Response Time |   550 ms |  316 ms |  43% Faster |
| P90               |   568 ms |  321 ms |  43% Faster |
| P95               |   612 ms |  328 ms |  46% Faster |
| P99               | 1,289 ms |  376 ms |  71% Faster |

### Key Findings

The optimized Lambda configuration processed significantly more requests while reducing response times across all latency percentiles.

Most notably:

* 72% increase in throughput
* 43% reduction in average response time
* 71% improvement in P99 latency
* Zero errors during testing

This exercise demonstrated that AWS Lambda memory allocation can have a substantial impact on application performance because additional memory also provides additional CPU resources.
