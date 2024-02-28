
# NODE.JS  Balanced Binary Search Tree Profiling

Balanced Binary Search Tree Implementation: https://github.com/Nazik3113/HSA1020/tree/master/bstree 

## MEMORY O(n)

| Elements | Memory used in MB |
| -------- | ----------------- |
| 10 000   |        16.4       |
| 1 000    |        1.7        |

16.4 / 1.7 ~= 10

## TIME O(log(n))

| Elements |     Time is ms    |
| -------- | ----------------- |
| 10 000   |        1925       |
| 1 000    |        138        |

log(1000) / log(10000) = 0.75

log(138) / log(1925) = 0.65 *похибка вийшла

Prerequisites:

  * NODE.JS just by itself cunsumes ~ 3.9 mb of memory to run the application.
  * We are using `--trace-gc` to measure memory usage.

Measurements on 10 000 elements:

```bash
$ node --trace-gc measurements.js 
...
[62976:0x5da38b0]      120 ms: Scavenge 4.6 (6.2) -> 3.7 (6.2) MB, 0.2 / 0.0 ms  (average mu = 1.000, current mu = 1.000) allocation failure 
[62976:0x5da38b0]      123 ms: Scavenge 4.6 (6.2) -> 3.7 (8.2) MB, 0.2 / 0.0 ms  (average mu = 1.000, current mu = 1.000) allocation failure 
[62976:0x5da38b0]      130 ms: Scavenge 5.6 (8.2) -> 3.7 (8.2) MB, 0.2 / 0.0 ms  (average mu = 1.000, current mu = 1.000) allocation failure 
[62976:0x5da38b0]      138 ms: Scavenge 5.6 (8.2) -> 3.7 (8.2) MB, 0.2 / 0.0 ms  (average mu = 1.000, current mu = 1.000) allocation failure

5.6 - 3.90 = 1.7
```

Measurements on 100 000 elements:

```bash
$ node --trace-gc measurements.js 
...
[72981:0x65678b0]     1588 ms: Scavenge 20.3 (37.2) -> 5.0 (37.2) MB, 0.6 / 0.0 ms  (average mu = 1.000, current mu = 1.000) allocation failure 
[72981:0x65678b0]     1704 ms: Scavenge 20.3 (37.2) -> 5.1 (37.2) MB, 0.7 / 0.0 ms  (average mu = 1.000, current mu = 1.000) allocation failure 
[72981:0x65678b0]     1823 ms: Scavenge 20.3 (37.2) -> 5.1 (37.2) MB, 0.7 / 0.0 ms  (average mu = 1.000, current mu = 1.000) allocation failure 
[72981:0x65678b0]     1925 ms: Scavenge 20.3 (37.2) -> 5.0 (37.2) MB, 0.7 / 0.0 ms  (average mu = 1.000, current mu = 1.000) allocation failure

20.3 - 3.9 = 16.4
```
