---
title: '[Python] BOJ 14652_나는 행복합니다~'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, Bronze]
toc: true
toc_sticky: true
date: 2020-05-22 02:13:30 -0400
last_modified_at: 2020-05-22T02:13:30+08:00
---

# 14652\_나는 행복합니다~

### 문제 링크

-   <https://www.acmicpc.net/problem/14652>{: target="\_blank"}

### 풀이 코드

```python
# 14652_나는 행복합니다~


import sys
input = sys.stdin.readline

n, m, k = map(int, input().split())

x = (k//m)
y = (k % m)
print(x, y)
```

### 비고
