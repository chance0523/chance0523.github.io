---
title: "[Python] BOJ 2748번. 피보나치 수 2"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ DP Silver5
meta_keywords: 알고리즘,백준,파이썬,2748번
date: 2020-05-13 02:08:18 -0400
---

# 2748번. 피보나치 수 2

### 문제 링크

- <https://www.acmicpc.net/problem/2748>{: target="\_blank"}

### 풀이 코드

```python
# 2748번. 피보나치 수 2n = int(input())

fibo = [0 for i in range(n+1)]
fibo[0] = 0
fibo[1] = 1
for i in range(2, n+1):
    fibo[i] = fibo[i-1]+fibo[i-2]
print(fibo[n])
```

### 비고
