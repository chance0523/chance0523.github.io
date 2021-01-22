---
title: "[Python] BOJ 12892번. 생일선물"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ slidingwindow Gold4
meta_keywords: 알고리즘,백준,파이썬,12892번
date: 2020-09-18 09:17:21 -0400
last_modified_at: 2020-09-18T09:17:21+08:00
---

# 12892번. 생일선물

### 문제 링크
- <https://www.acmicpc.net/problem/12892>{: target="\_blank"}

### 풀이 코드

```python
# 12892번. 생일선물


import sys
input = sys.stdin.readline


n, d = map(int, input().split())
nList = [0 for i in range(n)]
for i in range(n):
    nList[i] = list(map(int, input().split()))
nList.sort()

idx = []
maxhappy = nList[0][1]
s = maxhappy  # 합을 바꿀 변수
j = 0
# sliding
for i in range(1, n):
    s += nList[i][1]
    while nList[i][0]-nList[j][0] >= d:
        s -= nList[j][1]
        j += 1
    maxhappy = max(maxhappy, s)  # 최대값 비교

print(maxhappy)
```

### 비고