---
title: '[Python] BOJ 10250번. ACM 호텔'
excerpt: ''
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-13 13:26:25 -0400
last_modified_at: 2020-05-13T13:26:25+08:00
---

# 10250번. ACM 호텔

### 문제 링크

-   <https://www.acmicpc.net/problem/10250>{: target="\_blank"}

### 풀이 코드

```python
# 10250번. ACM 호텔

def hotel(h, w, n):
    y = n % h
    x = (n // h)+1
    if y == 0:
        y = h
        x -= 1
    return y*100+x


t = int(input())
for _ in range(t):
    h, w, n = map(int, input().split())
    print(hotel(h, w, n))
```

### 비고
