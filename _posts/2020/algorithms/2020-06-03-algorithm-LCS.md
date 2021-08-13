---
title: "[Python] BOJ 9251번. LCS"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, DP, Gold5]
toc: true
toc_sticky: true
date: 2020-06-03 01:43:51 -0400
last_modified_at: 2020-06-03T01:43:51+08:00
---

# 9251번. LCS

### 문제 링크

- <https://www.acmicpc.net/problem/9251>{: target="\_blank"}

### 풀이 코드

```python
# 9251번. LCS


import sys
input = sys.stdin.readline

a = list(input().rstrip())
b = list(input().rstrip())
dp = [[0 for i in range(len(a)+1)] for i in range(len(b)+1)]

for i in range(1, len(b)+1):
    for j in range(1, len(a)+1):
        if b[i-1] == a[j-1]:
            # 현재 위치의 값 = 왼쪽 대각선 값 + 1
            dp[i][j] = dp[i-1][j-1]+1
        else:
            # 현재 위치의 값 = max(왼쪽 값, 위쪽 값)
            dp[i][j] = max(dp[i-1][j], dp[i][j-1])

# 맨 마지막 dp가 최대
print(dp[-1][-1])
```

### 비고

- LCS 알고리즘 참고
- http://melonicedlatte.com/algorithm/2018/03/15/181550.html
