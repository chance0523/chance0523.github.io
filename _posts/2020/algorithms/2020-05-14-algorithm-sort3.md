---
title: "[Python] BOJ 10989번. 수 정렬하기 3"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ sort Silver4
meta_keywords: 알고리즘,백준,파이썬,10989번
date: 2020-05-14 23:12:02 -0400
last_modified_at: 2020-05-14T23:12:02+08:00
---

# 10989번. 수 정렬하기 3

### 문제 링크

- <https://www.acmicpc.net/problem/10989>{: target="\_blank"}

### 풀이 코드

```python
# 10989번. 수 정렬하기 3

input = sys.stdin.readline

n = int(input())
# 메모리에 주의 !!!
nList = [0]*10001

for i in range(n):
    nList[int(input())] += 1

for i in range(10001):
    if nList[i] != 0:
        for j in range(nList[i]):
            print(i)
```

### 비고
