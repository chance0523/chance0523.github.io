---
title: "[Python] BOJ 10800번 컬러볼"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ sort Gold3
meta_keywords: 알고리즘,백준,파이썬,10800번
date: 2020-09-06 22:47:31 -0400
last_modified_at: 2020-09-06T22:47:31+08:00
---

# 10800번 컬러볼

### 문제 링크
- <https://www.acmicpc.net/problem/10800>{: target="\_blank"}

### 풀이 코드

```python
# 10800번 컬러볼


import sys
input = sys.stdin.readline

'''
참조
https://mygumi.tistory.com/273
'''

n = int(input())
ball = [[0, 0, i] for i in range(n)]
ans = [0 for i in range(n)]
for i in range(n):
    ball[i][1], ball[i][0] = map(int, input().split())  # 크기가 먼저오게 담는다

ball.sort()
# 크기, 색상, 인덱스

colors = [0 for i in range(n+1)]
s = 0
j = 0
for i in range(n):
    while ball[j][0] < ball[i][0]:
        colors[ball[j][1]] += ball[j][0]
        s += ball[j][0]
        j += 1

    ans[ball[i][2]] = s - colors[ball[i][1]]

for i in range(n):
    print(ans[i])
```

### 비고