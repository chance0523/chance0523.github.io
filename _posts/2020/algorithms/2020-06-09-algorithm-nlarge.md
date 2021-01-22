---
title: "[Python] BOJ 2075번. N번째 큰 수"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ heapq Gold4
meta_keywords: 알고리즘,백준,파이썬,2075번
date: 2020-06-09 17:26:39 -0400
last_modified_at: 2020-06-09T17:26:39+08:00
---

# 2075번. N번째 큰 수

### 문제 링크
- <https://www.acmicpc.net/problem/2075>{: target="\_blank"}

### 풀이 코드

```python
# 2075번. N번째 큰 수


import heapq
import sys
input = sys.stdin.readline

n = int(input())
h = []
for i in range(n):
    # 한 줄 씩 보면서 비교해야 메모리 초과가 안 남
    nList = list(map(int, input().split()))
    for p in range(n):
        if len(h) == n:
            # 제일 작은 것을 꺼내서
            mi = heapq.heappop(h)
            # 지금 수와 비교
            if mi < nList[p]:
                # 지금 수가 더 크면 넣어줌
                heapq.heappush(h, (nList[p]))
            else:
                # 아니면 다시 넣어줌
                heapq.heappush(h, mi)
        else:
            heapq.heappush(h, (nList[p]))

# 다 끝나면 제일 작은 수를 출력
print(heapq.heappop(h))
```

### 비고