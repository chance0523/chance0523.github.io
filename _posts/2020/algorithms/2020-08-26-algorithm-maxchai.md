---
title: "[Python] BOJ 10819번. 차이를 최대로"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ bruteforce Silver2
meta_keywords: 알고리즘,백준,파이썬,10819번
date: 2020-08-26 00:53:20 -0400
last_modified_at: 2020-08-26T00:53:20+08:00
---

# 10819번. 차이를 최대로

### 문제 링크
- <https://www.acmicpc.net/problem/10819>{: target="\_blank"}

### 풀이 코드

```python
# 10819번. 차이를 최대로


from itertools import permutations
import sys
input = sys.stdin.readline

n = int(input())
nList = list(map(int, input().split()))
cList = list(permutations(nList))
maxans = 0
for c in cList:
    ans = 0
    for i in range(n-1):
        ans += abs(c[i]-c[i+1])
    if ans > maxans:
        maxans = ans
print(maxans)
```

### 비고