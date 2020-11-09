---
title: "[Python] BOJ 2309번. 일곱 난쟁이"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ bruteforce Bronze
meta_keywords: 알고리즘,백준,파이썬,2309번
date: 2020-06-29 20:47:57 -0400
last_modified_at: 2020-06-29T20:47:57+08:00
---

# 2309번. 일곱 난쟁이

### 문제 링크
- <https://www.acmicpc.net/problem/2309>{: target="\_blank"}

### 풀이 코드

```python
# 2309번. 일곱 난쟁이


from itertools import combinations
import sys
input = sys.stdin.readline

# 일곱 난쟁이의 키의 합이 100
nList = []
for i in range(9):
    nList.append(int(input()))
cList = list(combinations(nList, 7))
for i in range(len(cList)):
    if sum(cList[i]) == 100:
        for j in range(7):
            print(sorted(list(cList[i]))[j])
        break
```

### 비고