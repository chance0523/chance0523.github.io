---
title: "[Python] BOJ 10826번. 피보나치 수 4"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Silver3
meta_keywords: 알고리즘,백준,파이썬,10826번
date: 2020-06-09 20:27:25 -0400
last_modified_at: 2020-06-09T20:27:25+08:00
---

# 10826번. 피보나치 수 4

### 문제 링크
- <https://www.acmicpc.net/problem/10826>{: target="\_blank"}

### 풀이 코드

```python
# 10826번. 피보나치 수 4


n = int(input())

# n=0 일때를 따로 처리
if n == 0:
    print(0)
else:
    fibo = [0 for i in range(10001)]
    fibo[0] = 0
    fibo[1] = 1

    for i in range(2, n+1):
        fibo[i] = fibo[i-1]+fibo[i-2]

    print(fibo[n])
```

### 비고