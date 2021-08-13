---
title: "[Python] BOJ 14225번. 부분수열의 합"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-09-07 17:24:54 -0400
last_modified_at: 2020-09-07T17:24:54+08:00
---

# 14225번. 부분수열의 합

### 문제 링크
- <https://www.acmicpc.net/problem/14225>{: target="\_blank"}

### 풀이 코드

```python
# 14225번. 부분수열의 합


from itertools import combinations

n = int(input())
nList = list(map(int, input().split()))
nList.sort()

cList = []
for i in range(1, n+1):  # bruteforce
    cList.extend(list(combinations(nList, i)))

v = [0 for i in range(sum(cList[-1])+2)]  # 범위. 합으로 안 나오면 +1된것이 답

for c in cList:
    v[sum(c)] += 1

for i in range(1, len(v)+1):  # 범위.
    if v[i] == 0:
        print(i)
        break
```

### 비고