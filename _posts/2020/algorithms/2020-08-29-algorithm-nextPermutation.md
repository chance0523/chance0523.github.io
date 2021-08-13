---
title: "[Python] BOJ 12825번. Next Permutation"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-08-29 16:52:57 -0400
last_modified_at: 2020-08-29T16:52:57+08:00
---

# 12825번. Next Permutation

### 문제 링크
- <https://www.acmicpc.net/problem/12825>{: target="\_blank"}

### 풀이 코드

```python
# 12825번. Next Permutation


import sys
input = sys.stdin.readline

n = int(input())
nList = list(map(int, input().split()))

i = n-1
while i > 0 and nList[i-1] >= nList[i]:
    i -= 1
j = n-1
while nList[i-1] >= nList[j]:
    j -= 1
nList[i-1], nList[j] = nList[j], nList[i-1]

tList = [nList[k] for k in range(i)]
for k in range(j, n):
    tList.append(nList[k])
if abs(i-1-k) > 1:
    for k in range(j-1, i-1, -1):
        tList.append(nList[k])
print(*tList)
```

### 비고