---
title: '[Python] BOJ 11723번. 집합'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, Silver5]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,11723번
date: 2020-05-22 02:02:48 -0400
last_modified_at: 2020-05-22T02:02:48+08:00
---

# 11723번. 집합

### 문제 링크

-   <https://www.acmicpc.net/problem/11723>{: target="\_blank"}

### 풀이 코드

```python
# 11723번. 집합


import sys
input = sys.stdin.readline


def add(s, x):
    if x not in s:
        s.append(x)


def remove(s, x):
    if x in s:
        s.remove(x)


def check(s, x):
    if x in s:
        return 1
    else:
        return 0


def toggle(s, x):
    if x in s:
        s.remove(x)
    else:
        s.append(x)


def all(s):
    s = [i for i in range(1, 21)]
    return s


def empty(s):
    s = []
    return s


s = []

a = []
for i in range(int(input())):
    ip = input().rstrip()
    if ip == 'all':
        s = all(s)
    elif ip == 'empty':
        s = empty(s)
    else:
        c, x = ip.split()
        x = int(x)
        if c == 'add':
            add(s, x)
        elif c == 'remove':
            remove(s, x)
        elif c == 'check':
            print(check(s, x))
        elif c == 'toggle':
            toggle(s, x)

# print(a)
```

### 비고
