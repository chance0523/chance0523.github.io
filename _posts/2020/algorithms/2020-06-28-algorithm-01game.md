---
title: "[Python] codeforces edu90 B. 01 Game"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm codeforces games
meta_keywords: 알고리즘,코드포스,파이썬
date: 2020-06-28 02:46:02 -0400
last_modified_at: 2020-06-28T02:46:02+08:00
---

# B. 01 Game

### 문제 링크

- <https://codeforces.com/problemset/problem/1373/B>{: target="\_blank"}

### 풀이 코드

```python
# B. 01 Game


import sys
input = sys.stdin.readline

t = int(input())

for _ in range(t):
    s = list(input().rstrip())
    turn = False  # F for Alice, T for Bob
    i = 0
    while True:
        # if s empty
        if not s:
            break
        # all 0
        if '1' not in s:
            break
        # all 1
        if '0' not in s:
            break
        if s[i] != s[i+1]:
            del s[i:i+2]
            i = 0
            turn = not turn
        else:
            i += 1
    # print(turn)
    if turn:
        print('DA')
    else:
        print('NET')
```

### 비고
