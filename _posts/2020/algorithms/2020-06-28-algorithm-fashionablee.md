---
title: "[Python] codeforces #652 A. FashionabLee"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm codeforces geo
meta_keywords: 알고리즘,코드포스,파이썬
date: 2020-06-28 02:37:02 -0400
last_modified_at: 2020-06-28T02:37:02+08:00
---

# A. FashionabLee

### 문제 링크

- <https://codeforces.com/problemset/problem/1369/A>{: target="\_blank"}

### 풀이 코드

```python
# A. FashionabLee


import sys
input = sys.stdin.readline

t = int(input())
for i in range(t):
    n = int(input())
    if n % 4 == 0:
        print('YES')
    else:
        print('NO')
```

### 비고
