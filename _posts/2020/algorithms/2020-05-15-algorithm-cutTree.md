---
title: '[Python] BOJ 2805번. 나무 자르기'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 이분탐색, Silver3]
toc: true
toc_sticky: true
date: 2020-05-15 01:05:18 -0400
last_modified_at: 2020-05-15T01:05:18+08:00
---

# 2805번. 나무 자르기

### 문제 링크

-   <https://www.acmicpc.net/problem/2805>{: target="\_blank"}

### 풀이 코드

```python
# 2805번. 나무 자르기

# pypy로 해야 시간초과 없이 성공

import sys
input = sys.stdin.readline

n, m = map(int, input().split())
tList = list(map(int, input().split()))

left = 1
right = max(tList)

while left <= right:
    mid = (left+right)//2
    sum = 0
    for t in tList:
        if t >= mid:
            sum += (t-mid)
    if sum >= m:
        left = mid+1
    else:
        right = mid-1

print(right)
```

### 비고
