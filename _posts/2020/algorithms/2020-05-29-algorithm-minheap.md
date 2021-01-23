---
title: '[Python] BOJ 1927번. 최소 힙'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 힙, Silver1]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,1927번
date: 2020-05-29 16:06:38 -0400
last_modified_at: 2020-05-29T16:06:38+08:00
---

# 1927번. 최소 힙

### 문제 링크

-   <https://www.acmicpc.net/problem/1927>{: target="\_blank"}

### 풀이 코드

```python
# 1927번. 최소 힙


import heapq
import sys
input = sys.stdin.readline

n = int(input())
h = []
for i in range(n):
    ii = int(input())
    if ii != 0:
        heapq.heappush(h, ii)
    else:
        if not h:
            print(0)
        else:
            print(heapq.heappop(h))
```

### 비고
