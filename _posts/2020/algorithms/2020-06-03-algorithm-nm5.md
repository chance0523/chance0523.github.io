---
title: "[Python] BOJ 15654번. N과 M (5)"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-03 01:06:14 -0400
last_modified_at: 2020-06-03T01:06:14+08:00
---

# 15654번. N과 M (5)

### 문제 링크
- <https://www.acmicpc.net/problem/15654>{: target="\_blank"}

### 풀이 코드

```python
# 15654번. N과 M (5)


from itertools import permutations
import sys
input = sys.stdin.readline


n, m = map(int, input().split())
nList = list(map(int, input().split()))
# 순열로 만들어줌
pList = list(permutations(nList, m))
# 증가하는 순서로 출력하기 위함
pList.sort()

for p in pList:
    for i in range(m):
        # 같은 줄에 출력
        print(p[i], end=' ')
    print()

# 비슷한 문제 : https://www.acmicpc.net/problem/15650
```

### 비고