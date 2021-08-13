---
title: '[Python] BOJ 1085번. 직사각형에서 탈출'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, Bronze]
toc: true
toc_sticky: true
date: 2020-05-12 21:40:00 -0400
last_modified_at: 2020-05-12T21:40:18+08:00
---

# 1085번. 직사각형에서 탈출

### 문제 링크

-   <https://www.acmicpc.net/problem/1085>{: target="\_blank"}

### 풀이 코드

```python
# 1085번. 직사각형에서 탈출

x, y, w, h = map(int, input().split())

print(min(w-x, x, h-y, y))
```

### 비고
