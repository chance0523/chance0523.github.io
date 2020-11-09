---
title: "[Python] BOJ 10867번. 중복 빼고 정렬하기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ sort Silver5
meta_keywords: 알고리즘,백준,파이썬,10867번
date: 2020-06-11 12:24:58 -0400
last_modified_at: 2020-06-11T12:24:58+08:00
---

# 10867번. 중복 빼고 정렬하기

### 문제 링크
- <https://www.acmicpc.net/problem/10867>{: target="\_blank"}

### 풀이 코드

```python
# 10867번. 중복 빼고 정렬하기


n = int(input())

nset = set(map(int, input().split()))
nList = list(nset)
nList.sort()
for i in nList:
    print(i, end=' ')
```

### 비고