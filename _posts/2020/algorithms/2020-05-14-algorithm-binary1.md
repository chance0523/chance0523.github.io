---
title: "[Python] BOJ 11050번. 이항 계수 1"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ implement Bronze
meta_keywords: 알고리즘,백준,파이썬,11050번
date: 2020-05-14 01:20:10 -0400
last_modified_at: 2020-05-14T01:20:10+08:00
---

# 11050번. 이항 계수 1

### 문제 링크
- <https://www.acmicpc.net/problem/11050>{: target="\_blank"}

### 풀이 코드

```python
# 11050번. 이항 계수 1n, k = map(int, input().split())
if k == 0:
    print(1)
else:
    for i in range(n-k+1, n):
        n *= i

    for j in range(1, k):
        k *= j
    print(n//k)
```

### 비고