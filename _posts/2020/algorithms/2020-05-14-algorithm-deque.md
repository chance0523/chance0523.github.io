---
title: "[Python] BOJ 10866번. 덱"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ deque Silver4
meta_keywords: 알고리즘,백준,파이썬,10866번
date: 2020-05-14 12:37:07 -0400
last_modified_at: 2020-05-14T12:37:07+08:00
---

# 10866번. 덱

### 문제 링크
- <https://www.acmicpc.net/problem/10866>{: target="\_blank"}

### 풀이 코드

```python
# 10866번. 덱# 시간초과 방지용 readline
from collections import deque
import sys
input = sys.stdin.readline

n = int(input())
dq = deque()
for i in range(n):
    s = input().strip()
    if s.split()[0] == 'push_front':
        dq.appendleft(s.split()[1])
    elif s.split()[0] == 'push_back':
        dq.append(s.split()[1])
    elif s == 'pop_front':
        if not dq:
            print(-1)
        else:
            print(dq.popleft())
    elif s == 'pop_back':
        if not dq:
            print(-1)
        else:
            print(dq.pop())
    elif s == 'size':
        print(len(dq))
    elif s == 'empty':
        if not dq:
            print(1)
        else:
            print(0)
    elif s == 'front':
        if not dq:
            print(-1)
        else:
            print(dq[0])
    elif s == 'back':
        if not dq:
            print(-1)
        else:
            print(dq[-1])
```

### 비고