---
title: "[Python] BOJ 18119번. 단어 암기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ bruteforce Gold4
meta_keywords: 알고리즘,백준,파이썬,18119번
date: 2020-06-08 17:55:26 -0400
last_modified_at: 2020-06-08T17:55:26+08:00
---

# 18119번. 단어 암기

### 문제 링크
- <https://www.acmicpc.net/problem/18119>{: target="\_blank"}

### 풀이 코드

```python
# 18119번. 단어 암기


import sys
input = sys.stdin.readline

n, m = map(int, input().split())

wList = [0 for i in range(n)]
# 시간 초과 나서 비트마스크로..
# pypy3로 해야 초과 안남
for i in range(n):
    a = input().rstrip()
    for j in range(len(a)):
        wList[i] |= 1 << ord(a[j])-97

alpha = 0xffffffff
for _ in range(m):
    o, x = input().split()
    # 잘 생각해보면 연산이 왜 이렇게 되는지 알것이다
    if o == '1':
        alpha &= ~(1 << ord(x)-97)
    elif o == '2':
        alpha |= (1 << ord(x)-97)

    ans = 0
    for j in range(n):
        if (wList[j] & alpha) == wList[j]:
            ans += 1
    print(ans)
```

### 비고