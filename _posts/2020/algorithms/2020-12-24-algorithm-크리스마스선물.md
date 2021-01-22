---
title: "[Python] BOJ 14235번. 크리스마스 선물"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ priorityQueue Silver3
meta_keywords: 알고리즘,백준,파이썬,14235번
date: 2020-12-24 00:19:42 -0400
last_modified_at: 2020-12-24T00:19:42+08:00
---

# 14235번. 크리스마스 선물

### 문제 링크
- <https://www.acmicpc.net/problem/14235>{: target="\_blank"}

### 풀이 코드

```python
# 14235번. 크리스마스 선물


import heapq
n = int(input())
present = []
for i in range(n):
    aList = list(map(int, input().split()))
    a = aList[0]
    if a == 0:  # 아이들에게 선물을 줘야함 (제일 큰 가치)
        if present:  # 줄 선물이 있으면
            print(heapq.heappop(present)[1])
        else:  # 줄 선물이 없으면
            print(-1)
    else:
        for j in range(1, a+1):  # 첫번째 숫자는 a
            heapq.heappush(present, (-aList[j], aList[j]))
```

### 비고