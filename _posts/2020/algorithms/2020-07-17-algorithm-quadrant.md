---
title: "[Python] BOJ 14681번. 사분면 고르기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Bronze
meta_keywords: 알고리즘,백준,파이썬,14681번
date: 2020-07-17 21:04:05 -0400
last_modified_at: 2020-07-17T21:04:05+08:00
---

# 14681번. 사분면 고르기

### 문제 링크
- <https://www.acmicpc.net/problem/14681>{: target="\_blank"}

### 풀이 코드

```python
# 14681번. 사분면 고르기


x = int(input())
y = int(input())

if x > 0:
    if y > 0:
        print(1)
    else:
        print(4)
else:
    if y > 0:
        print(2)
    else:
        print(3)
```

### 비고