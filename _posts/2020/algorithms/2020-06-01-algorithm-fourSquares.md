---
title: "[Python] BOJ 17626번. Four Squares"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Implement, Silver5]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,17626번
date: 2020-06-01 20:47:12 -0400
last_modified_at: 2020-06-01T20:47:12+08:00
---

# 17626번. Four Squares

### 문제 링크
- <https://www.acmicpc.net/problem/17626>{: target="\_blank"}

### 풀이 코드

```python
# 17626번. Four Squares


import sys
input = sys.stdin.readline

n = int(input())
ans = 4  # 최대값은 4
for i in range(int(n**0.5), int((n//4)**0.5), -1):
    if i**2 == n:
        ans = 1
        break
    else:
        tmp = n-i**2  # i^2을 빼고 남은 수를 생각
        for j in range(int(tmp**0.5), int((tmp//3)**0.5), -1):
            if i**2+j**2 == n:
                ans = min(ans, 2)
                continue
            else:
                tmp = n-i**2-j**2
                for k in range(int(tmp**0.5), int((tmp//2)**0.5), -1):
                    if n == i**2+j**2+k**2:
                        ans = min(ans, 3)
print(ans)
```

### 비고