---
title: "[Python] BOJ 2108번. 통계학"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Silver4
meta_keywords: 알고리즘,백준,파이썬,2108번
date: 2020-05-14 16:34:00 -0400
last_modified_at: 2020-05-14T16:34:00+08:00
---

# 2108번. 통계학

### 문제 링크

- <https://www.acmicpc.net/problem/2108>{: target="\_blank"}

### 풀이 코드

```python
# 2108번. 통계학

from collections import Counter
# 그나마 sys 써야 시간 초과 안남...
import sys
input = sys.stdin.readline


def mean(nList):
    return round(sum(nList)/n)


def median(nList):
    if n == 1:
        return nList[0]
    else:
        # n==홀수
        return nList[n//2]


def mode(nList):
    if n == 1:
        return nList[0]
    else:
        c = Counter(nList).most_common(2)
        if c[0][1] == c[1][1]:
            return c[1][0]
        else:
            return c[0][0]


def mM(nList):
    return (nList[-1]-nList[0])


n = int(input())
nList = sorted([int(input()) for _ in range(n)])

print(mean(nList))
print(median(nList))
print(mode(nList))
print(mM(nList))
```

### 비고
