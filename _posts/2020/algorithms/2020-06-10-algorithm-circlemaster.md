---
title: "[Python] BOJ 16481번. 원 전문가 진우"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-10 01:35:30 -0400
last_modified_at: 2020-06-10T01:35:30+08:00
---

# 16481번. 원 전문가 진우

### 문제 링크
- <https://www.acmicpc.net/problem/16481>{: target="\_blank"}

### 풀이 코드

```python
# 16481번. 원 전문가 진우


# https://m.blog.naver.com/mondvopel/220216908924
# 1/r = 1/r1 + 1/r2 + 1/r3

r1, r2, r3 = map(int, input().split())

r = 1/r1+1/r2+1/r3
print(1/r)
```

### 비고