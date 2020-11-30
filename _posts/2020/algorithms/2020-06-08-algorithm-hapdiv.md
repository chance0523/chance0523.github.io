---
title: "[Python] BOJ 2225번. 분해합"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ DP Gold5
meta_keywords: 알고리즘,백준,파이썬,2225번
date: 2020-06-08 16:31:33 -0400
last_modified_at: 2020-06-08T16:31:33+08:00
---

# 2225번. 분해합

### 문제 링크
- <https://www.acmicpc.net/problem/2225>{: target="\_blank"}

### 풀이 코드

```python
# 2225번. 분해합


n, k = map(int, input().split())

dp = [[0 for i in range(k+1)] for i in range(n+1)]

# dp[n][k] : n을 k개 정수의 합으로 표현 경우의 수

for i in range(n+1):
    dp[i][1] = 1

mod = 1000000000

for i in range(1, k+1):
    for j in range(n+1):
        for p in range(j+1):
            dp[j][i] += dp[p][i-1]
            # 계속 mod로 나눠주면서
            dp[j][i] %= mod

print(dp[n][k])
```

### 비고