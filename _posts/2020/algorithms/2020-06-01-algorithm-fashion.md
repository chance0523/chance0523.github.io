---
title: '[Python] BOJ 9375번. 패션왕 신해빈'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-01 21:39:33 -0400
last_modified_at: 2020-06-01T21:39:33+08:00
---

# 9375번. 패션왕 신해빈

### 문제 링크

-   <https://www.acmicpc.net/problem/9375>{: target="\_blank"}

### 풀이 코드

```python
# 9375번. 패션왕 신해빈


from itertools import combinations
from itertools import product
from collections import defaultdict
import sys
input = sys.stdin.readline

t = int(input())
for _ in range(t):
    n = int(input())
    cDict = {}
    ans = 1
    for i in range(n):
        name, kind = input().rstrip().split()
        if kind not in cDict:
            cDict[kind] = 1
        else:
            cDict[kind] += 1
    for key in cDict.keys():
        ans = ans*(cDict[key]+1)  # 입는 것 + 안 입는 것
    print(ans-1)  # 알몸인 경우 -1
```

### 비고
