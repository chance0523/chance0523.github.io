---
title: "[Python] BOJ 1697번. 숨바꼭질"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 그래프, Silver1]
toc: true
toc_sticky: true
categories: Algorithm BOJ graph Silver1
meta_keywords: 알고리즘,백준,파이썬,1697번
date: 2020-05-29 20:12:17 -0400
last_modified_at: 2020-05-29T20:12:17+08:00
---

# 1697번. 숨바꼭질

### 문제 링크

-   <https://www.acmicpc.net/problem/1697>{: target="\_blank"}

### 풀이 코드

```python
# 1697번. 숨바꼭질


from collections import deque
import sys
input = sys.stdin.readline


def bfs(v):
    cnt = 0
    q = deque([[v, cnt]])
    while q:
        v = q.popleft()
        vv = v[0]
        cnt = v[1]
        if not visited[vv]:
            visited[vv] = True
            if vv == k:
                return cnt
            cnt += 1
            if vv*2 <= 100000:
                q.append([vv*2, cnt])
            if vv+1 <= 100000:
                q.append([vv+1, cnt])
            if vv-1 >= 0:
                q.append([vv-1, cnt])
    return cnt


# n, k = 5, 17
n, k = map(int, input().split())

visited = [False]*100001
print(bfs(n))
```

### 비고
