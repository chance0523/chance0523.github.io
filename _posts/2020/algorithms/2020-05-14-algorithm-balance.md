---
title: '[Python] BOJ 4949번. 균형잡힌 세상'
excerpt: ''
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-14 17:23:23 -0400
last_modified_at: 2020-05-14T17:23:23+08:00
---

# 4949번. 균형잡힌 세상

### 문제 링크

-   <https://www.acmicpc.net/problem/4949>{: target="\_blank"}

### 풀이 코드

```python
# 4949번. 균형잡힌 세상

import sys
input = sys.stdin.readline

while True:
    sList = input().rstrip()
    if sList == '.':
        break
    stack = []
    f = True
    for s in sList:
        if s == '(' or s == '[':
            stack.append(s)
        elif s == ')':

            if stack and stack[-1] == '(':
                stack.pop()
            else:
                f = False
                break
        elif s == ']':
            if stack and stack[-1] == '[':
                stack.pop()
            else:
                f = False
                break
    if not stack and f == True:
        print('yes')
    else:
        print('no')
```

### 비고
