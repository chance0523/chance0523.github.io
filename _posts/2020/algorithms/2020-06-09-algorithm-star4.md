---
title: "[Python] BOJ 2441번. 별 찍기 - 4"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-09 19:43:50 -0400
last_modified_at: 2020-06-09T19:43:50+08:00
---

# 2441번. 별 찍기 - 4

### 문제 링크
- <https://www.acmicpc.net/problem/2441>{: target="\_blank"}

### 풀이 코드

```python
# 2441번. 별 찍기 - 4


n = int(input())
for i in range(n):
    print(' '*i+'*'*(n-i))
```

### 비고