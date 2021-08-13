---
title: "[Python] BOJ 20499번. Darius님 한타 안 함?"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-12-30 23:15:24 -0400
last_modified_at: 2020-12-30T23:15:24+08:00
---

# 20499번. Darius님 한타 안 함?

### 문제 링크
- <https://www.acmicpc.net/problem/20499>{: target="\_blank"}

### 풀이 코드

```python
# 20499번. Darius님 한타 안 함?


k, d, a = map(int, input().split('/'))
if k + a < d or d == 0:
    print('hasu')
else:
    print('gosu')
```

### 비고