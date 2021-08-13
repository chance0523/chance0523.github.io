---
title: "[Python] BOJ 1916번. 최소비용 구하기"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-30 19:28:29 -0400
last_modified_at: 2020-06-30T19:28:29+08:00
---

# 1916번. 최소비용 구하기

### 문제 링크
- <https://www.acmicpc.net/problem/1916>{: target="\_blank"}

### 풀이 코드

```python
# 1916번. 최소비용 구하기


import heapq
import sys
input = sys.stdin.readline


n = int(input())
m = int(input())
s = [[] for i in range(n+1)]
dist = [1e9 for i in range(n+1)]
for i in range(m):
    start, end, cost = map(int, input().split())
    s[start].append([end, cost])
# 구하고자 하는 출발, 도착 번호
start, end = map(int, input().split())


def dijkstra(start):
    dist[start] = 0
    heap = []
    heapq.heappush(heap, [dist[start], start])
    while heap:
        curDis, curNode = heapq.heappop(heap)
        if dist[curNode] < curDis:
            continue
        for a, w in s[curNode]:
            distance = curDis+w
            if distance < dist[a]:
                dist[a] = distance
                heapq.heappush(heap, [distance, a])
    return dist


dijkstra(start)
print(dist[end])
```

### 비고