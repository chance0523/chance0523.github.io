---
title: '[Python] BOJ 1074번. Z'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, Silver1]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,1074번
date: 2020-05-29 04:15:13 -0400
last_modified_at: 2020-05-29T04:15:13+08:00
---

# 1074번. Z

### 문제 링크

-   <https://www.acmicpc.net/problem/1074>{: target="\_blank"}

### 풀이 코드

```python
# 1074번. Z


import sys
input = sys.stdin.readline


# n, r, c = 2, 3, 1
# n, r, c = 3, 7, 7
n, r, c = map(int, input().split())
cnt = 0


while n >= 1:

    if n == 1:  # 2x2 사각형
        # 1사분면일때는 그대로
        if r == 0 and c == 1:  # 2사분면
            cnt += 1
        elif r == 1 and c == 0:  # 3사분면
            cnt += 2
        elif r == 1 and c == 1:  # 4사분면
            cnt += 3
        break

    # 사각형을 4등분하였을 때의 기준을 temp
    temp = 2**(n-1)
    # 1사분면일때는 그대로
    if r < temp <= c:  # 2사분면
        # z에서 첫번째로 가는 곳이 2사분면
        cnt += temp**2
        c -= temp
    elif c < temp <= r:  # 3사분면
        # z에서 두번째로 가는 곳이 3사분면
        cnt += (temp**2)*2
        r -= temp
    elif temp <= r and temp <= c:  # 4사분면
        # z에서 세번째로 가는 곳이 4사분면
        cnt += (temp**2)*3
        c -= temp
        r -= temp

    n -= 1

print(cnt)
```

### 비고
