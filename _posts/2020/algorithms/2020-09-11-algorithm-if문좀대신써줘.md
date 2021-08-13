---
title: "[Python] BOJ 19637번. IF문 좀 대신 써줘"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-09-11 01:45:35 -0400
last_modified_at: 2020-09-11T01:45:35+08:00
---

# 19637번. IF문 좀 대신 써줘

### 문제 링크
- <https://www.acmicpc.net/problem/19637>{: target="\_blank"}

### 풀이 코드

```python
# 19637번. IF문 좀 대신 써줘


import sys
input = sys.stdin.readline
# 다시 풀어볼 문제...
n, m = map(int, input().split())

cost = []  # 전투력 관리
name = []  # 칭호만 관리
for i in range(n):
    a, b = input().rstrip().split()
    cost.append(int(b))
    name.append(a)
i = 0
while i < len(cost)-1:
    if cost[i] == cost[i+1]:
        cost.pop(i+1)
        name.pop(i+1)
    i += 1

t = []
for i in range(m):
    t.append([int(input()), i, 0])
t.sort()
for i in range(len(cost)):
    if t[0][0] <= cost[i]:
        t[0][2] = name[i]
        idx = i
        break

for i in range(m):
    if t[i][0] <= cost[idx]:
        t[i][2] = name[idx]
    else:
        idx += 1
        while True:
            if t[i][0] <= cost[idx]:
                t[i][2] = name[idx]
                break
            idx += 1
ans = [0 for i in range(m)]

for i in range(m):
    ans[t[i][1]] = t[i][2]
for i in range(m):
    print(ans[i])
```

### 비고