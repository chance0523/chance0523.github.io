---
title: "[Python] BOJ 9655번. 돌게임"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-12-21 22:15:55 -0400
last_modified_at: 2020-12-21T22:15:55+08:00
---

# 9655번. 돌게임

### 문제 링크
- <https://www.acmicpc.net/problem/9655>{: target="\_blank"}

### 풀이 코드

```python
# 9655번. 돌게임


n = int(input())
# 돌은 홀수개씩 줄어듬
if n % 2 == 1:
    print('SK')
else:
    print('CY')

# print('SK' if int(input()) % 2 else 'CY')
```

### 비고