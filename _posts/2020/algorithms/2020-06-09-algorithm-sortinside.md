---
title: "[Python] BOJ 1427번. 소트인사이트"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-09 21:09:22 -0400
last_modified_at: 2020-06-09T21:09:22+08:00
---

# 1427번. 소트인사이트

### 문제 링크
- <https://www.acmicpc.net/problem/1427>{: target="\_blank"}

### 풀이 코드

```python
# 1427번. 소트인사이트


s = list(input())
s.sort(reverse=True)
for i in range(len(s)):
    print(s[i], end='')
```

### 비고