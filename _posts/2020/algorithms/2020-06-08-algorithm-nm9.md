---
title: "[Python] BOJ 15663번. N과 M (9)"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Implement, Silver2]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,15663번
date: 2020-06-08 18:43:28 -0400
last_modified_at: 2020-06-08T18:43:28+08:00
---

# 15663번. N과 M (9)

### 문제 링크
- <https://www.acmicpc.net/problem/15663>{: target="\_blank"}

### 풀이 코드

```python
# 15663번. N과 M (9)


from itertools import permutations
n, m = map(int, input().split())
nList = list(map(int, input().split()))
# nList.sort()
cList = list(set(permutations(nList, m)))
cList.sort()
for c in cList:
    for i in c:
        print(i, end=' ')
    print()
```

### 비고