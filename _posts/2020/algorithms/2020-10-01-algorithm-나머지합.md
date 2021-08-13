---
title: "[Python] BOJ 10986번. 나머지합"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-10-01 01:19:06 -0400
last_modified_at: 2020-10-01T01:19:06+08:00
---

# 10986번. 나머지합

### 문제 링크
- <https://www.acmicpc.net/problem/10986>{: target="\_blank"}

### 풀이 코드

```python
# 10986번. 나머지합


n, m = map(int, input().split())
nList = list(map(int, input().split()))

# prefix sum
su = 0
s = [0 for i in range(1001)]
s[0] = 1
for i in range(n):
    su += nList[i]  # 구간 합 구하고
    su %= m  # 나머지만 넣기
    s[su] += 1

# combinations
ans = 0
for i in range(m):
    # 나머지가 같은것끼리 빼면 결국 나머지가 0이 됨
    ans += s[i]*(s[i]-1)/2

print(int(ans))
```

### 비고