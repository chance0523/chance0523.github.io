---
title: "[Python] BOJ 2407번. 조합"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Silver2
meta_keywords: 알고리즘,백준,파이썬,2407번
date: 2020-06-03 01:12:53 -0400
last_modified_at: 2020-06-03T01:12:53+08:00
---

# 2407번. 조합

### 문제 링크
- <https://www.acmicpc.net/problem/2407>{: target="\_blank"}

### 풀이 코드

```python
# 2407번. 조합


import sys
input = sys.stdin.readline

n, m = map(int, input().split())

son = 1  # 분자
for i in range(n-m+1, n+1):
    son *= i

mom = 1  # 분모
for i in range(1, m+1):
    mom *= i

ans = son//mom
print(ans)
```

### 비고