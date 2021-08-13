---
title: '[Python] BOJ 2908번. 상수'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, 문자열, Bronze]
toc: true
toc_sticky: true
date: 2020-05-12 21:21:00 -0400
last_modified_at: 2020-05-12T21:21:00+08:00
---

# 2908번. 상수

### 문제 링크

-   <https://www.acmicpc.net/problem/2908>{: target="\_blank"}

### 풀이 코드

무조건 세자리수이기 때문에 덧셈으로 구현

```python
# 2908번. 상수

a, b = input().split(' ')
a = a[2]+a[1]+a[0]
b = b[2]+b[1]+b[0]
print(max(a, b))

```

### 비고
