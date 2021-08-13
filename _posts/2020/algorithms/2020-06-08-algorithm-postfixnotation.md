---
title: "[Python] BOJ 1918번. 후위 표기식"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-08 19:34:54 -0400
last_modified_at: 2020-06-08T19:34:54+08:00
---

# 1918번. 후위 표기식

### 문제 링크
- <https://www.acmicpc.net/problem/1918>{: target="\_blank"}

### 풀이 코드

```python
# 1918번. 후위 표기식


a = input().rstrip()

priority = {
    '*': 2,
    '/': 2,
    '+': 1,
    '-': 1,
    '(': 0
}
stack = []

for c in '('+a+')':
    # print('\n', stack)
    if 'A' <= c <= 'Z':
        print(c, end='')
    elif c == '(':
        stack.append(c)
    elif c == ')':
        while True:
            o = stack.pop()
            if o == '(':
                break
            print(o, end='')
    else:
        while stack[-1] != '(' and priority[c] <= priority[stack[-1]]:
            print(stack.pop(), end='')
        stack.append(c)
```

### 비고