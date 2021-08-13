---
title: "[Python] BOJ 1010번. 다리놓기"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-08-19 08:04:04 -0400
last_modified_at: 2020-08-19T08:04:04+08:00
---

# 1010번. 다리놓기

### 문제 링크
- <https://www.acmicpc.net/problem/1010>{: target="\_blank"}

### 풀이 코드

```python
# 1010번. 다리놓기


s = [[0 for i in range(30)] for i in range(30)]
for i in range(1, 30):
    s[1][i] = i
for i in range(2, 30):
    for j in range(i, 30):
        for k in range(i-1, j):
            s[i][j] += s[i-1][k]
for i in range(int(input())):
    n, m = map(int, input().split())
    print(s[n][m])
```

### 비고