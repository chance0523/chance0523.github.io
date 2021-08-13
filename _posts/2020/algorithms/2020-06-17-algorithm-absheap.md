---
title: "[Python] BOJ 11286번. 절댓값 힙"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-17 22:17:32 -0400
last_modified_at: 2020-06-17T22:17:32+08:00
---

# 11286번. 절댓값 힙

### 문제 링크
- <https://www.acmicpc.net/problem/11286>{: target="\_blank"}

### 풀이 코드

```python
# 11286번. 절댓값 힙


import heapq
import sys
input = sys.stdin.readline

n = int(input())
h = []
ans = []
for i in range(n):
    ii = int(input())
    if ii != 0:
        # heapq는 최소 힙.
        # 절댓값, 원본을 같이 넣어줌
        heapq.heappush(h, [abs(ii), ii])
    else:
        if not h:
            print(0)
        else:
            print((heapq.heappop(h))[1])
```

### 비고