---
title: "[Python] BOJ 1085번. 직사각형에서 탈출"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Bronze3
meta_keywords: 알고리즘,백준,파이썬,1085번
date: 2020-05-12 21:40:00 -0400
---

# 1085번. 직사각형에서 탈출

### 문제 링크

- <https://www.acmicpc.net/problem/1085>{: target="\_blank"}

### 풀이 코드

```python
# 1085번. 직사각형에서 탈출

x, y, w, h = map(int, input().split())

print(min(w-x, x, h-y, y))
```

### 비고
