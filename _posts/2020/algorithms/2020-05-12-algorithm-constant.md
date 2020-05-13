---
title: "[Python] BOJ 2908번. 상수"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement String Bronze2
meta_keywords: 알고리즘,백준,파이썬,2908번
date: 2020-05-12 21:21:00 -0400
---

# 2908번. 상수

### 문제 링크

- <https://www.acmicpc.net/problem/2908>{: target="\_blank"}

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
