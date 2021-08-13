---
title: "[Python] BOJ 1915번. 가장 큰 정사각형"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-12-12 13:36:27 -0400
last_modified_at: 2020-12-12T13:36:27+08:00
---

# 1915번. 가장 큰 정사각형

### 문제 링크
- <https://www.acmicpc.net/problem/1915>{: target="\_blank"}

### 풀이 코드

```python
# 1915번. 가장 큰 정사각형


n, m = map(int, input().split())

nList = [list(map(int, input().rstrip())) for i in range(n)]

ans = 0

for i in range(n):
    for j in range(m):
        if i and j and nList[i][j] == 1:
            # 11
            # 11
            nList[i][j] += min(nList[i - 1][j], nList[i]
                               [j - 1], nList[i - 1][j - 1])
        ans = max(ans, nList[i][j])

print(ans**2)
```

### 비고