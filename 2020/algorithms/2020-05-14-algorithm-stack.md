---
title: "[Python] BOJ 10828번. 스택"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ stack Silver4
meta_keywords: 알고리즘,백준,파이썬,10828번
date: 2020-05-14 12:29:07 -0400
last_modified_at: 2020-05-14T12:29:07+08:00
---

# 10828번. 스택

### 문제 링크

- <https://www.acmicpc.net/problem/10828>{: target="\_blank"}

### 풀이 코드

```python
# 10828번. 스택

# 시간초과 방지용 readline
import sys

input = sys.stdin.readline

n = int(input())
stack = []
for i in range(n):
    s = input().strip()
    if s.split()[0] == 'push':
        stack.append(int(s.split()[1]))
    elif s == 'pop':
        if not stack:
            print(-1)
        else:
            print(stack.pop())
    elif s == 'size':
        print(len(stack))
    elif s == 'empty':
        if not stack:
            print(1)
        else:
            print(0)
    elif s == 'top':
        if not stack:
            print(-1)
        else:
            print(stack[-1])
```

### 비고
