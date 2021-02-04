---
title: "[Python] BOJ 16750번. N과 M(2)"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Implement, Silver3]
toc: true
meta_keywords: 알고리즘,백준,파이썬,15650번
date: 2020-06-03 00:59:22 -0400
last_modified_at: 2020-06-03T00:59:22+08:00
---

# 16750번. N과 M(2)

### 문제 링크
- <https://www.acmicpc.net/problem/15650>{: target="\_blank"}

### 풀이 코드

```python
# 16750번. N과 M(2)


from itertools import combinations
import sys
input = sys.stdin.readline

# n, m = 3, 1
# n, m = 4, 2
n, m = map(int, input().split())
nList = [i for i in range(1, n+1)]
# 조합 사용
cList = list(combinations(nList, m))

for c in cList:
    for i in range(m):
        # 요소를 한 줄에 출력
        print(c[i], end=' ')
    # 한 칸 띄어줌
    print()
```

### 비고