---
title: "[Python] BOJ 1009번. 분산처리"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-12-19 02:51:12 -0400
last_modified_at: 2020-12-19T02:51:12+08:00
---

# 1009번. 분산처리

### 문제 링크
- <https://www.acmicpc.net/problem/1009>{: target="\_blank"}

### 풀이 코드

```python
# 1009번. 분산처리


import sys
input = sys.stdin.readline

for _ in range(int(input())):
    a, b = map(int, input().split())
    ans = 1
    for i in range(b):  # a^b 계산
        ans *= a  # 곱해주고
        m = ans % 10 # 1의 자리수가 중요하다
        if m == 0: # 0이면 10
            ans = 10
        else:
            ans %=10
    print(ans)
```

### 비고