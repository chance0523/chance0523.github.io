---
title: "[Python] BOJ 2581번. 소수"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ prime Silver4
meta_keywords: 알고리즘,백준,파이썬,2581번
date: 2020-06-30 07:51:28 -0400
last_modified_at: 2020-06-30T07:51:28+08:00
---

# 2581번. 소수

### 문제 링크
- <https://www.acmicpc.net/problem/2581>{: target="\_blank"}

### 풀이 코드

```python
# 2581번. 소수


m = int(input())
n = int(input())

primeList = [False for i in range(10001)]
# 소수는 false
for i in range(2, int(10000**0.5)+1):
    if not primeList[i]:
        for j in range(i+i, 10000, i):
            primeList[j] = True
primeList[1] = True
primeList[10000] = True

ansList = []
for i in range(m, n+1):
    if not primeList[i]:
        ansList.append(i)
if len(ansList) == 0:
    print(-1)
else:
    print(sum(ansList))
    print(ansList[0])
```

### 비고