---
title: "[Python] BOJ 19637번. IF문 좀 대신 써줘"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ binary_search Silver2
meta_keywords: 알고리즘,백준,파이썬,19637번
date: 2020-12-15 16:08:29 -0400
last_modified_at: 2020-12-15T16:08:29+08:00
---

# 19637번. IF문 좀 대신 써줘

### 문제 링크
- <https://www.acmicpc.net/problem/19637>{: target="\_blank"}

### 풀이 코드

```python
# 19637번. IF문 좀 대신 써줘


import sys
input = sys.stdin.readline

n, m = map(int, input().split())
powerList = []
nameList = []
for i in range(n):
    name, power = input().split()
    power = int(power)
    if powerList and powerList[-1] == power:  # 가장 처음 칭호만 저장해주기 위해
        continue
    powerList.append(power)
    nameList.append(name)


def binary_search(p):
    left = 0
    right = len(powerList) - 1
    while left <= right:
        mid = (left + right) // 2
        if p > powerList[mid]:
            left = mid + 1
        else:
            right = mid - 1
    print(nameList[right+1])


mList = []
for _ in range(m):
    p = int(input())
    binary_search(p)  # 이분탐색
```

### 비고