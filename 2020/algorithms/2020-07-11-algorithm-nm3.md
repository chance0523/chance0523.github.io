---
title: "[Python] BOJ 15651번. N과 M (3)"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Silver3
meta_keywords: 알고리즘,백준,파이썬,15651번
date: 2020-07-11 23:44:42 -0400
last_modified_at: 2020-07-11T23:44:42+08:00
---

# 15651번. N과 M (3)

### 문제 링크
- <https://www.acmicpc.net/problem/15651>{: target="\_blank"}

### 풀이 코드

```python
# 15651번. N과 M (3)


from itertools import product
import sys
input = sys.stdin.readline

n, m = map(int, input().split())
nList = [i for i in range(1, n+1)]
# 중복순열로 쉽게 구현
cList = list(product(nList, repeat=m))

for c in cList:
    print(*c)
```

### 비고