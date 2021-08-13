---
title: '[Python] BOJ 10870번. 피보나치 수 5'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-09 20:24:53 -0400
last_modified_at: 2020-06-09T20:24:53+08:00
---

# 10870번. 피보나치 수 5

### 문제 링크

-   <https://www.acmicpc.net/problem/10870>{: target="\_blank"}

### 풀이 코드

```python
# 10870번. 피보나치 수 5


n = int(input())

# n=0 일때를 따로 처리
if n == 0:
    print(0)
else:
    fibo = [0 for i in range(50)]
    fibo[0] = 0
    fibo[1] = 1

    for i in range(2, n+1):
        fibo[i] = fibo[i-1]+fibo[i-2]

    print(fibo[n])
```

### 비고
