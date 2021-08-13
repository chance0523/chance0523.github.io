---
title: "[Python] BOJ 15657번. N과 M (8)"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-08 18:37:45 -0400
last_modified_at: 2020-06-08T18:37:45+08:00
---

# 15652번. N과 M (8)

### 문제 링크

- <https://www.acmicpc.net/problem/15657>{: target="\_blank"}

### 풀이 코드

```python
# 15657번. N과 M (8)


from itertools import combinations_with_replacement
n, m = map(int, input().split())
nList = list(map(int, input().split()))
nList.sort()
cList = list(combinations_with_replacement(nList, m))

for c in cList:
    for i in c:
        print(i, end=' ')
    print()
```

### 비고
