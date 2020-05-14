---
title: "[Python] BOJ 4153번. 직각삼각형"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Bronze
meta_keywords: 알고리즘,백준,파이썬,4153번
date: 2020-05-14 14:56:31 -0400
last_modified_at: 2020-05-14T14:56:31+08:00
---

# 4153번. 직각삼각형

### 문제 링크
- <https://www.acmicpc.net/problem/4153>{: target="\_blank"}

### 풀이 코드

```python
# 4153번. 직각삼각형while True:
    nList = list(map(int, input().split()))
    nList.sort()
    if nList[0] == 0:
        break
    else:
        a = nList[0]**2
        b = nList[1]**2
        c = nList[2]**2
        if c == a+b:
            print('right')
        else:
            print('wrong')
```

### 비고