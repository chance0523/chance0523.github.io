---
title: "[Python] codeforces global8 A. C+="
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm codeforces bruteforce
meta_keywords: 알고리즘,코드포스,파이썬
date: 2020-06-28 02:36:02 -0400
last_modified_at: 2020-06-28T02:36:02+08:00
---

# A. C+=

### 문제 링크

- <https://codeforces.com/problemset/problem/1368/A>{: target="\_blank"}

### 풀이 코드

```python
# A. C+=


import sys
input = sys.stdin.readline

t = int(input())

for i in range(t):
    a, b, n = map(int, input().split())
    ans = 0
    M = max(a, b)
    '''
    5 4
    9 4 / 5 9
    '''
    while n >= M:
        # 두 개 합이 큰 것으로 계속 가면 됨
        if (a+b)+b > a+(a+b):
            a += b
        else:
            b += a
        M = max(a, b)
        ans += 1
    print(ans)
```

### 비고
