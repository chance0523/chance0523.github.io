---
title: "[Python] BOJ 2166번. 다각형의 면적"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ geo Gold5
meta_keywords: 알고리즘,백준,파이썬,2166번
date: 2020-08-25 22:19:46 -0400
last_modified_at: 2020-08-25T22:19:46+08:00
---

# 2166번. 다각형의 면적

### 문제 링크
- <https://www.acmicpc.net/problem/2166>{: target="\_blank"}

### 풀이 코드

```python
# 2166번. 다각형의 면적


# https://darkpgmr.tistory.com/86
import sys
input = sys.stdin.readline


n = int(input())
nList = [[0, 0] for i in range(n+1)]

for i in range(n):
    a, b = map(int, input().split())
    nList[i][0] = a
    nList[i][1] = b

nList[n][0] = nList[0][0]
nList[n][1] = nList[0][1]

s = 0
for i in range(n):
    s += ((nList[i][0]*nList[i+1][1])/2 - (nList[i+1][0]*nList[i][1])/2)
if s < 0:
    s *= -1
s = round(s, 1)
print(s)
```

### 비고