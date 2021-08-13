---
title: "[Python] BOJ 2491번. 수열"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-09-19 00:52:46 -0400
last_modified_at: 2020-09-19T00:52:46+08:00
---

# 2491번. 수열

### 문제 링크
- <https://www.acmicpc.net/problem/2491>{: target="\_blank"}

### 풀이 코드

```python
# 2491번. 수열


import sys
input = sys.stdin.readline

n = int(input())
nList = list(map(int, input().split()))

inc = 1  # 증가하는 구간 길이
dec = 1  # 감소하는 구간 길이
ans = 1  # 배열 길이가 1이라면 답은 1

for i in range(n-1):
    if nList[i] < nList[i+1]:  # 증가
        inc += 1  # 증가구간 길이++
        ans = max(ans, inc)  # 최대 길이
        dec = 1  # 감소구간 길이 초기화
    elif nList[i] > nList[i+1]:  # 감소
        dec += 1
        ans = max(ans, dec)
        inc = 1
    else:  # 같은 때. 둘 다 늘려주고 비교
        inc += 1
        ans = max(ans, inc)
        dec += 1
        ans = max(ans, dec)
print(ans)
```

### 비고