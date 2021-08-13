---
title: '[Python] BOJ 1003번. 피보나치 함수'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-22 03:48:12 -0400
last_modified_at: 2020-05-22T03:48:12+08:00
---

# 1003번. 피보나치 함수

### 문제 링크

-   <https://www.acmicpc.net/problem/1003>{: target="\_blank"}

### 풀이 코드

```python
# 1003번. 피보나치 함수


t = int(input())

dp = [[1, 0], [0, 1]]

# dp[i][0]끼리 피보나치, dp[i][1]끼리 피보나치를 이룬다.

for i in range(2, 41):
    dp.append([dp[i-1][0]+dp[i-2][0], dp[i-1][1]+dp[i-2][1]])

for i in range(t):
    ii = int(input())
    print(dp[ii][0], dp[ii][1])
```

### 비고
