---
title: "[Python] BOJ 14652_나는 행복합니다~"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Bronze
meta_keywords: 알고리즘,백준,파이썬,14652번
date: 2020-05-22 02:13:30 -0400
last_modified_at: 2020-05-22T02:13:30+08:00
---

# 14652_나는 행복합니다~

### 문제 링크
- <https://www.acmicpc.net/problem/14652>{: target="\_blank"}

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