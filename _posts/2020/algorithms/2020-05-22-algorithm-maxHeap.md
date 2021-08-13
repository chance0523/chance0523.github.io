---
title: '[Python] BOJ 11279번. 최대 힙'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 힙, Silver2]
toc: true
toc_sticky: true
date: 2020-05-22 04:17:19 -0400
last_modified_at: 2020-05-22T04:17:19+08:00
---

# 11279번. 최대 힙

### 문제 링크

-   <https://www.acmicpc.net/problem/11279>{: target="\_blank"}

### 풀이 코드

```python
# 11279번. 최대 힙


import heapq
import sys
input = sys.stdin.readline

n = int(input())
h = []
for i in range(n):
    ii = int(input())
    if ii != 0:
        # heapq는 최소 힙.
        # 최대 힙으로 바꾸기 위해 input을 음수로 바꿔줌
        heapq.heappush(h, (-ii))
    else:
        if not h:
            print(0)
        else:
            print(-1 * heapq.heappop(h))
```

### 비고
