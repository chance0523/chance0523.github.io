---
title: '[Python] BOJ 2475번. 검증수'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Bronze5]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,2475번
date: 2020-05-12 12:23:00 -0400
last_modified_at: 2020-05-12T12:23:00+08:00
---

# 2475번. 검증수

### 문제 링크

-   <https://www.acmicpc.net/problem/2475>{: target="\_blank"}

### 풀이 코드

```python
# 2475번. 검증수

a1, a2, a3, a4, a5 = map(int, input().split(' '))
v = (a1*a1+a2*a2+a3*a3+a4*a4+a5*a5) % 10
print(v)
```

### 비고

-   브론즈5
