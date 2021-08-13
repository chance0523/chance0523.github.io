---
title: "[Python] BOJ 15666번. N과 M (12)"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-08 18:47:21 -0400
last_modified_at: 2020-06-08T18:47:21+08:00
---

# 15666번. N과 M (12)

### 문제 링크
- <https://www.acmicpc.net/problem/15666>{: target="\_blank"}

### 풀이 코드

```python
# 15666번. N과 M (12)


from itertools import combinations_with_replacement
n, m = map(int, input().split())
nList = list(map(int, input().split()))
nList.sort()
cList = list(set(combinations_with_replacement(nList, m)))
cList.sort()

for c in cList:
    for i in c:
        print(i, end=' ')
    print()
```

### 비고