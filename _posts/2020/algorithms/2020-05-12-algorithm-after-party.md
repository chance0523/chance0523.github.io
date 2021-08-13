---
title: '[Python] BOJ 2845번. 파티가 끝나고 난 뒤'
excerpt: ''
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-12 12:30:00 -0400
last_modified_at: 2020-05-12T12:30:00+08:00
---

# 2845번. 파티가 끝나고 난 뒤

### 문제 링크

-   <https://www.acmicpc.net/problem/2845>{: target="\_blank"}

### 풀이 코드

```python
# 2845번. 파티가 끝나고 난 뒤

l, p = map(int, input().split(' '))
a1, a2, a3, a4, a5 = map(int, input().split(' '))
t = l*p  # total
b1 = a1-t
b2 = a2-t
b3 = a3-t
b4 = a4-t
b5 = a5-t
print(b1, b2, b3, b4, b5)
```

### 비고

-   브론즈5
