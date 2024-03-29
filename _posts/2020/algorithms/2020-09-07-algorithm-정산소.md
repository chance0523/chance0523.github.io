---
title: "[Python] BOJ 11735번. 정산소"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-09-07 17:10:43 -0400
last_modified_at: 2020-09-07T17:10:43+08:00
---

# 11735번. 정산소

### 문제 링크
- <https://www.acmicpc.net/problem/11735>{: target="\_blank"}

### 풀이 코드

```python
# 11735번. 정산소


import sys
input = sys.stdin.readline

n, q = map(int, input().split())

rcnt = 0
ccnt = 0
rdel = 0
cdel = 0
hap = n*(n+1)//2

vr = [0 for i in range(n+1)]
vc = [0 for i in range(n+1)]

'''
n*k + [1..n] 
n*k 에서는 현재까지 나온 열의 갯수를 빼주고
[1..n] 에서는 현재까지 나온 열 값의 합을 빼준다.
천천히 이해
'''

for i in range(q):
    a, b = input().split()
    b = int(b)
    if a == 'R':
        if vr[b] == 1:  # 이미 나온 쿼리 (0)
            print(0)
        else:
            vr[b] = 1  # 방문처리
            print((n-ccnt)*b + hap - cdel)
            rcnt += 1
            rdel += b
    else:
        if vc[b] == 1:  # 이미 나온 쿼리 (0)
            print(0)
        else:
            vc[b] = 1  # 방문처리
            print((n-rcnt)*b + hap - rdel)
            ccnt += 1
            cdel += b
```

### 비고