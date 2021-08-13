---
title: '[Python] BOJ 1654번. 랜선 자르기'
excerpt: ''
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-14 23:26:18 -0400
last_modified_at: 2020-05-14T23:26:18+08:00
---

# 1654번. 랜선 자르기

### 문제 링크

-   <https://www.acmicpc.net/problem/1654>{: target="\_blank"}

### 풀이 코드

```python
# 1654번. 랜선 자르기

import sys
input = sys.stdin.readline

k, n = map(int, input().split())
lan = [int(input()) for i in range(k)]

left, right = 1, max(lan)
while left <= right:
    mid = (left+right)//2
    lines = 0
    for i in lan:
        lines += (i//mid)
    if lines >= n:
        left = mid+1  # 어디까지 늘릴 수 있나 보자
    else:
        right = mid-1
print(right)


'''
이렇게 풀면 시간초과
for i in range(min(lan), 1, -1):
    sum = 0
    for j in range(len(lan)):
        sum += (lan[j]//i)
    if sum == n:
        print(i)
        break
'''
```

### 비고
