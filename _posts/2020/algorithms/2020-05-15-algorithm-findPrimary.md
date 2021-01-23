---
title: '[Python] BOJ 1929번. 소수 구하기'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, Silver2]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,1929번
date: 2020-05-15 01:59:56 -0400
last_modified_at: 2020-05-15T01:59:56+08:00
---

# 1929번. 소수 구하기

### 문제 링크

-   <https://www.acmicpc.net/problem/1929>{: target="\_blank"}

### 풀이 코드

```python
# 1929번. 소수 구하기

import sys
input = sys.stdin.readline

m, n = map(int, input().split())
max = 1000000


# 에라스토테네스의 체
def etc(max):
    pList = [True]*max
    mnum = int(max**0.5)
    for i in range(2, mnum+1):
        if pList[i]:
            for j in range(i+i, max, i):
                pList[j] = False
        else:
            continue
    return [i for i in range(2, max) if pList[i]]


pList = etc(max)
for p in pList:
    if p >= m and p <= n:
        print(p)
```

### 비고
