---
title: "[Python] BOJ 2747번. 피보나치 수"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Bronze
meta_keywords: 알고리즘,백준,파이썬,2747번
date: 2020-06-09 20:23:23 -0400
last_modified_at: 2020-06-09T20:23:23+08:00
---

# 2747번. 피보나치 수

### 문제 링크
- <https://www.acmicpc.net/problem/2747>{: target="\_blank"}

### 풀이 코드

```python
# 2747번. 피보나치 수


fibo = [0 for i in range(50)]
fibo[0] = 0
fibo[1] = 1

n = int(input())
for i in range(2, n+1):
    fibo[i] = fibo[i-1]+fibo[i-2]

print(fibo[n])
```

### 비고