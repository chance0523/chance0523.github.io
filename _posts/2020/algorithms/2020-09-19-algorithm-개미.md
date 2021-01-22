---
title: "[Python] BOJ 10158번. 개미"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Silver5
meta_keywords: 알고리즘,백준,파이썬,10158번
date: 2020-09-19 18:09:43 -0400
last_modified_at: 2020-09-19T18:09:43+08:00
---

# 10158번. 개미

### 문제 링크
- <https://www.acmicpc.net/problem/10158>{: target="\_blank"}

### 풀이 코드

```python
# 10158번. 개미


import sys
input = sys.stdin.readline

w, h = map(int, input().split())
p, q = map(int, input().split())
t = int(input())

# 개미는 오른쪽 위 45도 방향으로 먼저 움직임
garo = (p+t)//w
sero = (q+t)//h

# garo=0 이면 오른쪽으로 가는 중, 1이면 왼쪽으로 가는중 ...
r = (p+t) % w
if garo % 2 == 1:
    r = w-r
c = (q+t) % h
if sero % 2 == 1:
    c = h-c
print(r, c)
```

### 비고