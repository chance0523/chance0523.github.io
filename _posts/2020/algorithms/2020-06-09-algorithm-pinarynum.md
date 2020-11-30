---
title: "[Python] BOJ 2193번. 이친수"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ DP Silver3
meta_keywords: 알고리즘,백준,파이썬,2193번
date: 2020-06-09 03:18:05 -0400
last_modified_at: 2020-06-09T03:18:05+08:00
---

# 2193번. 이친수

### 문제 링크
- <https://www.acmicpc.net/problem/2193>{: target="\_blank"}

### 풀이 코드

```python
# 2193번. 이친수


n = int(input())

dp = [[0 for i in range(2)] for i in range(n+1)]
# dp[자리수][끝자리숫자]

dp[1][0] = 1
dp[1][1] = 1

# 끝자리 숫자가 0이면 그 앞자리는 아무거나
# 끝자리 숫자가 1이면 무조건 0

for i in range(2, n+1):
    dp[i][0] = dp[i-1][0]+dp[i-1][1]
    dp[i][1] = dp[i-1][0]

print(dp[n][1])
print(dp)
```

### 비고