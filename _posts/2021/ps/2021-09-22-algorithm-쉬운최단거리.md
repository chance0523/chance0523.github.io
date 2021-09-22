---
title: '[Python] BOJ 14940번. 쉬운 최단거리'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-09-22 11:00:25 -0400
last_modified_at: 2021-09-22T11:00:25+08:00
---

# 14940번. 쉬운 최단거리

### 문제 링크
- <https://www.acmicpc.net/problem/14940>{: target="\_blank"}

### 풀이 코드
- BFS를 연습해볼 수 있는 간단한 문제입니다.
- `원래 갈 수 없는 땅인 위치는 0을 출력하고, 원래 갈 수 있는 땅인 부분 중에서 도달할 수 없는 위치는 -1을 출력한다.` 이 문장이 문제의 핵심인데, 저는 제대로 읽지 못하고 bfs를 통해 갈 수 없는 땅도 -1로 해서 한 번 틀렸습니다.
```python
# 위 문장을 제대로 지키지 않았을 때의 반례
2 2
2 0
0 0

# 출력
0 0
0 -1

# 실제 답
0 0
0 0
```

- 이 부분만 유의하여 풀어준다면 쉽게 풀립니다.

```python
# 14940번. 쉬운 최단거리


from collections import deque
import sys

# 입력
n, m = map(int, input().rstrip().split())
box = [0 for _ in range(n)]
tr, tc = 0, 0  # 목표지점
for i in range(n):
    box[i] = list(map(int, input().rstrip().split()))
    for j in range(len(box[i])):
        if box[i][j] == 2: # 목표지점 저장
            tr, tc = i, j

# 답을 출력할 리스트
ans = [[-1 for _ in range(m)] for _ in range(n)] # 방문 할 수 없는 곳은 -1

# 원래 갈 수 없는 땅인 위치는 0으로 고정
for i in range(n):
    for j in range(m):
        if box[i][j] == 0:
            ans[i][j] = 0

# 방문 리스트
v = [[False for _ in range(m)] for _ in range(n)]

# BFS
q = deque([[tr, tc, 0]])
ans[tr][tc] = 0
dx = [-1, 1, 0, 0]
dy = [0, 0, 1, -1]

while q:
    t = q.popleft()
    cr, cc, cnt = t[0], t[1], t[2]
    if v[cr][cc]:
        continue
    v[cr][cc] = True
    for d in range(4):
        nr = cr + dx[d]
        nc = cc + dy[d]
        if 0 <= nr < n and 0 <= nc < m and not v[nr][nc]:
            if box[nr][nc] == 1:
                ans[nr][nc] = cnt + 1
                q.append([nr, nc, cnt + 1])

# 출력
for i in range(n):
    print(*ans[i])
```

### 비고