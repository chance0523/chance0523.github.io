---
title: '[Python] BOJ 1012번. 유기농 배추'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-29 16:33:12 -0400
last_modified_at: 2020-05-29T16:33:12+08:00
---

# 1012번. 유기농 배추

### 문제 링크

-   <https://www.acmicpc.net/problem/1012>{: target="\_blank"}

### 풀이 코드

```python
# 1012번. 유기농 배추


import sys
input = sys.stdin.readline
sys.setrecursionlimit(50000)

dx = [0, 1, -1, 0]
dy = [1, 0, 0, -1]


def dfs(y, x):
    box[y][x] = 0
    for i in range(4):
        ny = y+dy[i]
        nx = x+dx[i]
        if nx < 0 or ny < 0 or ny >= n or nx >= m:
            continue
        if box[ny][nx] == 1:
            dfs(ny, nx)


t = int(input())
for _ in range(t):
    m, n, k = map(int, input().split())  # 가로 m, 세로 n
    box = [[0 for i in range(m)] for i in range(n)]
    for i in range(k):
        x, y = map(int, input().split())
        box[y][x] = 1

    cnt = 0
    for i in range(n):
        for j in range(m):
            if box[i][j] == 1:
                dfs(i, j)
                cnt += 1
    print(cnt)
```

### 비고
