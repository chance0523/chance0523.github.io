---
title: '[Python] BOJ 2749번. 피보나치 수 3'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Implement, Gold2]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,2749번
date: 2020-06-09 20:49:17 -0400
last_modified_at: 2020-06-09T20:49:17+08:00
---

# 2749번. 피보나치 수 3

### 문제 링크

-   <https://www.acmicpc.net/problem/2749>{: target="\_blank"}

### 풀이 코드

```python
# 2749번. 피보나치 수 3


n = int(input())
fibo = [0, 1]
mod = 1000000

# 피보나치 수를 나눈 수는 항상 주기를 가진다.
# 피보나치 수를 나눌 수를  k라고 할 때, k=10^n이면
# 주기는 15*10^(n-1)이다.

p = mod//10*15  # 피보나치 수를 나눈 수의 주기

for i in range(2, p):
    fibo.append(fibo[i-1]+fibo[i-2])
    fibo[i] %= mod

print(fibo[n % p])
```

### 비고
