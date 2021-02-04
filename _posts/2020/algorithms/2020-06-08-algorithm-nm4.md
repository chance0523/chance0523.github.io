---
title: "[Python] BOJ 15652번. N과 M (4)"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Implement, Silver3]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,15652번
date: 2020-06-08 18:34:01 -0400
last_modified_at: 2020-06-08T18:34:01+08:00
---

# 15652번. N과 M (4)

### 문제 링크
- <https://www.acmicpc.net/problem/15652>{: target="\_blank"}

### 풀이 코드

```python
# 15652번. N과 M (4)


from itertools import combinations_with_replacement
n, m = map(int, input().split())
nList = [i for i in range(1, n+1)]

cList = list(combinations_with_replacement(nList, m))

for c in cList:
    for i in c:
        print(i, end=' ')
    print(end='\n')
```

### 비고