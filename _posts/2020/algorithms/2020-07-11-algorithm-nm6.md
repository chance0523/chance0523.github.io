---
title: "[Python] BOJ 15655번. N과 M (6)"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-07-11 23:44:46 -0400
last_modified_at: 2020-07-11T23:44:46+08:00
---

# 15655번. N과 M (6)

### 문제 링크
- <https://www.acmicpc.net/problem/15655>{: target="\_blank"}

### 풀이 코드

```python
# 15655번. N과 M (6)


from itertools import combinations
import sys
input = sys.stdin.readline

n, m = map(int, input().split())
nList = list(map(int, input().split()))
nList.sort()
cList = list(combinations(nList, m))

for c in cList:
    print(*c)
```

### 비고