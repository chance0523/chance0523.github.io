---
title: "[Python] BOJ 11656번. 접미사 배열"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ sort Silver4
meta_keywords: 알고리즘,백준,파이썬,11656번
date: 2020-11-30 04:43:45 -0400
last_modified_at: 2020-11-30T04:43:45+08:00
---

# 11656번. 접미사 배열

### 문제 링크
- <https://www.acmicpc.net/problem/11656>{: target="\_blank"}

### 풀이 코드

```python
# 11656번. 접미사 배열


s = input()
sList = []
for i in range(len(s)):
    sList.append(s[i: len(s)])
sList.sort()
for k in sList:
    print(k)
```

### 비고