---
title: "[Python] BOJ 11660번. 구간 합 구하기 5"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-08 17:12:32 -0400
last_modified_at: 2020-06-08T17:12:32+08:00
---

# 11660번. 구간 합 구하기 5

### 문제 링크
- <https://www.acmicpc.net/problem/11660>{: target="\_blank"}

### 풀이 코드

```python
# 11660번. 구간 합 구하기 5


# pypy3로 해야 시간초과 안남
import sys
input = sys.stdin.readline


n, m = map(int, input().split())
box = [[] for i in range(n)]
for i in range(n):
    box[i] = list(map(int, input().split()))

# 열별로 sum
for i in range(n):
    for j in range(n):
        if j == 0:
            pass
        else:
            box[i][j] += box[i][j-1]

for _ in range(m):
    x1, y1, x2, y2 = map(int, input().split())

    ans = 0
    for i in range(x1-1, x2):
        # y2까지 합을 x 범위에서 구하고
        ans += box[i][y2-1]
        # y1 전까지의 합을 빼준다
        if y1 != 1:
            ans -= box[i][y1-2]
    print(ans)
```

### 비고