---
title: "[Python] BOJ 4811번. 알약"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-12-13 20:27:07 -0400
last_modified_at: 2020-12-13T20:27:07+08:00
---

# 4811번. 알약

### 문제 링크
- <https://www.acmicpc.net/problem/4811>{: target="\_blank"}

### 풀이 코드

```python
# 4811번. 알약


import sys
input = sys.stdin.readline
sys.setrecursionlimit(50000)


def dfs(w, h):
    if dp[w][h]:
        return dp[w][h]

    if w == 0:  # 한 조각짜리가 없으면 무조건 반조각 짜리를 꺼내야
        return 1

    dp[w][h] = dfs(w - 1, h + 1)

    if h > 0:
        dp[w][h] += dfs(w, h - 1)  # 이런 경우도 더해주기

    return dp[w][h]


dp = [[0 for i in range(31)] for i in range(31)]

while True:
    n = int(input())

    if n == 0:
        break
    print(dfs(n, 0))  # 처음에는 완전한 n개의 알약이 있음
```

### 비고