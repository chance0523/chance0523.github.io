---
title: '[Python] BOJ 1259번. 팰린드롬수'
excerpt: ''
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-13 13:43:11 -0400
last_modified_at: 2020-05-13T13:43:11+08:00
---

# 1259번. 팰린드롬수

### 문제 링크

-   <https://www.acmicpc.net/problem/1259>{: target="\_blank"}

### 풀이 코드

```python
# 1259번. 팰린드롬수

def p(n):
    if n[0] != n[-1]:
        return 'no'
    else:
        i = 1
        while i <= (len(n)//2):
            if n[i] != n[-i-1]:
                return 'no'
            else:
                i += 1
        return 'yes'


while True:
    n = input()
    if n == '0':
        break
    print(p(n))
```

### 비고
