---
title: "[Python] BOJ 11727번. 2×n 타일링 2"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-01 23:00:55 -0400
last_modified_at: 2020-06-01T23:00:55+08:00
---

# 11727번. 2×n 타일링 2

### 문제 링크

- <https://www.acmicpc.net/problem/11727>{: target="\_blank"}

### 풀이 코드

```python
# 11727번. 2×n 타일링 2


import sys
input = sys.stdin.readline

n = int(input())
dp = [0 for i in range(n+1)]
dp[0] = 1
dp[1] = 1
# dp[2] = 3 이걸 쓰면 n=1인 경우 때문에 런타임 에러
# dp[3] = dp[1]*2+dp[2]
# dp[n] = (dp[n-1]+dp[n-2]*2)
for i in range(2, n+1):
    dp[i] = (dp[i-1]+dp[i-2]*2) % 10007
print(dp[n])
```

### 비고
