---
title: "[Python] BOJ 10157번. 자리배정"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Silver5
meta_keywords: 알고리즘,백준,파이썬,10157번
date: 2020-09-19 13:25:05 -0400
last_modified_at: 2020-09-19T13:25:05+08:00
---

# 10157번. 자리배정

### 문제 링크
- <https://www.acmicpc.net/problem/10157>{: target="\_blank"}

### 풀이 코드

```python
# 10157번. 자리배정


import sys
input = sys.stdin.readline

c, r = map(int, input().split())
k = int(input())
box = [[0 for i in range(c)] for i in range(r)]

if k > r*c:  # 좌석을 배치할 수 없을 때
    print(0)
    sys.exit()

cnt = 1  # 배정될 좌석
dir = 0  # 방향
dx = [-1, 0, 1, 0]  # 상우하좌
dy = [0, 1, 0, -1]

cr = r-1
cc = 0
while True:
    if cnt == k:
        print((cc+1), (r-cr))
        break
    box[cr][cc] = cnt
    nr = cr+dx[dir]
    nc = cc+dy[dir]
    if nr < 0 or nc < 0 or nr >= r or nc >= c or box[nr][nc] != 0:
        dir = (dir+1) % 4  # 방향전환
        nr = cr + dx[dir]
        nc = cc + dy[dir]

    cr = nr
    cc = nc
    cnt += 1
```

### 비고