---
title: '[Python] BOJ 9012번. 괄호'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, Silver4]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,9012번
date: 2020-05-14 02:43:23 -0400
last_modified_at: 2020-05-14T02:43:23+08:00
---

# 9012번. 괄호

### 문제 링크

-   <https://www.acmicpc.net/problem/9012>{: target="\_blank"}

### 풀이 코드

```python
# 9012번. 괄호

t = int(input())


def isVPS(sList):
    cnt = 0
    for s in sList:
        if cnt == 0:
            if s == '(':
                cnt += 1
            # )이 먼저 나오면 NO
            elif s == ')':
                return 'NO'
        else:
            if s == '(':
                cnt += 1
            elif s == ')':
                cnt -= 1
    if cnt == 0:
        return 'YES'
    else:
        return 'NO'


for i in range(t):
    sList = list(input())
    print(isVPS(sList))
```

### 비고
