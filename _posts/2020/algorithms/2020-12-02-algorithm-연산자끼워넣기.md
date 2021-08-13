---
title: "[Python] BOJ 14888번. 연산자 끼워넣기"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-12-02 01:52:16 -0400
last_modified_at: 2020-12-02T01:52:16+08:00
---

# 14888번. 연산자 끼워넣기

### 문제 링크
- <https://www.acmicpc.net/problem/14888>{: target="\_blank"}

### 풀이 코드

```python
# 14888번. 연산자 끼워넣기


import sys
input = sys.stdin.readline


def place(cnt, result, p, mi, mul, d):
    global minAns, maxAns
    if cnt == n:  # 연산자 다 썼을 때
        minAns = min(minAns, result)
        maxAns = max(maxAns, result)
        return
    if p:
        place(cnt+1, result+nList[cnt], p-1, mi, mul, d)
    if mi:
        place(cnt+1, result-nList[cnt], p, mi-1, mul, d)
    if mul:
        place(cnt+1, result*nList[cnt], p, mi, mul-1, d)
    if d:
        if result < 0:
            place(cnt+1, -(abs(result)//nList[cnt]), p, mi, mul, d-1)
        else:
            place(cnt+1, abs(result)//nList[cnt], p, mi, mul, d-1)


n = int(input())
nList = list(map(int, input().split()))
p, mi, mul, d = map(int, input().split())
minAns = 1e9+1
maxAns = -1e9-1

place(1, nList[0], p, mi, mul, d)

print(maxAns)
print(minAns)
```

### 비고