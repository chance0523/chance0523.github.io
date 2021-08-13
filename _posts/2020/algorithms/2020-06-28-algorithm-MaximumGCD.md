---
title: "[Python] codeforces #651 A. Maximum GCD"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-28 02:41:02 -0400
last_modified_at: 2020-06-28T02:41:02+08:00
---

# A. Maximum GCD

### 문제 링크

- <https://codeforces.com/problemset/problem/1370/A>{: target="\_blank"}

### 풀이 코드

```python
# A. Maximum GCD


import sys
input = sys.stdin.readline

t = int(input())
for i in range(t):
    n = int(input())
    if n == 1:
        print(1)
    elif n % 2 == 1:
        print((n-1)//2)
    else:
        print(n//2)
```

### 비고
