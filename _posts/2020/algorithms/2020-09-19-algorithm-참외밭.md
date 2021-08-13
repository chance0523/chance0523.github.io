---
title: "[Python] BOJ 2477번. 참외밭"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-09-19 00:57:39 -0400
last_modified_at: 2020-09-19T00:57:39+08:00
---

# 2477번. 참외밭

### 문제 링크
- <https://www.acmicpc.net/problem/2477>{: target="\_blank"}

### 풀이 코드

```python
# 2477번. 참외밭


import sys
input = sys.stdin.readline

n = int(input())
nList = []
w = h = w2 = h2 = 0
for i in range(6):
    dir, l = map(int, input().split())
    nList.append(l)
    # 가로와 세로의 최대값을 정해줌 (큰 사각형)
    if i % 2 == 0:
        w = max(w, l)
    else:
        h = max(h, l)

for i in range(6):
    if i % 2 == 0 and h == nList[(i+5) % 6]+nList[(i+1) % 6]:
        w2 = nList[i]
    elif i % 2 == 1 and w == nList[(i+5) % 6]+nList[(i+1) % 6]:
        h2 = nList[i]
print(n*(w*h - w2*h2))
```

### 비고