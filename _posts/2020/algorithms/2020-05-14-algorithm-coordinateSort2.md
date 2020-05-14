---
title: "[Python] BOJ 11651번. 좌표 정렬하기 2"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ sort Silver5
meta_keywords: 알고리즘,백준,파이썬,11651번
date: 2020-05-14 16:04:31 -0400
last_modified_at: 2020-05-14T16:04:31+08:00
---

# 11651번. 좌표 정렬하기 2

### 문제 링크
- <https://www.acmicpc.net/problem/11651>{: target="\_blank"}

### 풀이 코드

```python
# 11651번. 좌표 정렬하기 2n = int(input())
nList = []
for i in range(n):
    x, y = map(int, input().split())
    # x,y를 반대로 넣어서 정렬하고 반대로 빼는 것이 중요
    nList.append((y, x))
nList.sort()
for y, x in nList:
    print(x, y)
```

### 비고