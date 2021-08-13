---
title: '[Python] BOJ 4386번. 별자리 만들기'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-07-26 11:30:25 -0400
last_modified_at: 2021-07-26T11:30:25+08:00
---

# 4386번. 도시 분할 계획

### 문제 링크
- <https://www.acmicpc.net/problem/4386>{: target="\_blank"}

### 풀이 코드
- 전형적인 MST 문제입니다.
- 입력이 시작점,끝점,비용으로 주어지는 대신, 점들의 좌표로 주어집니다.
- 먼저 좌표를 다 받은 다음 (시작점, 끝점, 비용)을 만들어서 edge에 넣어주면 됩니다.
- 그 뒤에는 소수점만 신경쓰며 MST로 뚝딱! EASY~

```python
# 4386번. 별자리 만들기


import math
def make(parent):
    for i in range(v + 1):
        parent[i] = i
    return parent


def find(parent, a):
    if parent[a] == a:
        return a
    parent[a] = find(parent, parent[a])
    return parent[a]


def union(parent, a, b):
    a = find(parent, a)
    b = find(parent, b)
    if a > b:
        parent[a] = b
        return True
    elif a < b:
        parent[b] = a
        return True
    return False

n = int(input())
# 별들의 좌표를 넣어준다.
stars = []
for i in range(n):
    x,y = map(float,input().split())
    stars.append([x,y])
# MST 활용을 위해 (거리,시작,끝)을 만든다.
parent = [i for i in range(n+1)]
edges = []
for i in range(n-1):
    for j in range(i+1,n):
        start = stars[i]
        end = stars[j]
        distance = math.sqrt((start[0]-end[0])**2 + (start[1]-end[1])**2)
        edges.append([distance,i,j])
edges.sort()

cnt, ans = 0,0
# U-F
for edge in edges:
    if union(parent, edge[1], edge[2]):
        ans += edge[0]
        cnt += 1
        if cnt == n - 1:
            break

print(round(ans,2))
```

### 비고