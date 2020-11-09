---
title: "[Python] BOJ 13023번. ABCDE"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ graph Gold5
meta_keywords: 알고리즘,백준,파이썬,13023번
date: 2020-09-02 00:44:47 -0400
last_modified_at: 2020-09-02T00:44:47+08:00
---

# 13023번. ABCDE

### 문제 링크
- <https://www.acmicpc.net/problem/13023>{: target="\_blank"}

### 풀이 코드

```python
# 13023번. ABCDE


import sys
input = sys.stdin.readline

n, m = map(int, input().split())
box = [[] for i in range(n)]
for i in range(m):
    a, b = map(int, input().split())
    box[a].append(b)
    box[b].append(a)

visited = [False for i in range(n)]


def dfs(index, cnt):
    global ans

    visited[index] = True

    if(cnt == 4):
        ans = True
        return

    for v in box[index]:
        if not visited[v]:
            dfs(v, cnt+1)
            visited[v] = False


ans = False
for i in range(n):
    dfs(i, 0)
    visited[i] = False
    if ans:
        break

print(1 if ans else 0)
```

### 비고