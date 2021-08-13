---
title: '[Python] BOJ 11650번. 좌표 정렬하기'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 정렬, Silver5]
toc: true
toc_sticky: true
date: 2020-05-14 02:15:20 -0400
last_modified_at: 2020-05-14T02:15:20+08:00
---

# 11650번. 좌표 정렬하기

### 문제 링크

-   <https://www.acmicpc.net/problem/11650>{: target="\_blank"}

### 풀이 코드

```python
# 11650번. 좌표 정렬하기

n = int(input())
cList = []
for i in range(n):
    x, y = map(int, input().split())
    cList.append((x, y))

cList.sort()

for x, y in cList:
    print(x, y)
```

### 비고
