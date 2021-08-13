---
title: '[Python] BOJ 2609번. 최대공약수와 최소공배수'
excerpt: ''
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-14 01:57:57 -0400
last_modified_at: 2020-05-14T01:57:57+08:00
---

# 2609번. 최대공약수와 최소공배수

### 문제 링크

-   <https://www.acmicpc.net/problem/2609>{: target="\_blank"}

### 풀이 코드

```python
# 2609번. 최대공약수와 최소공배수

a, b = map(int, input().split())
gcd = 0
lcm = 0

mi = min(a, b)
ma = max(a, b)

# GCD : a,b중 더 작은 것에서부터 시작
for i in range(mi, 0, -1):
    if a % i == 0 and b % i == 0:
        gcd = i
        break

# lcm : 더 작은 수의 배수가 큰 수로 나누어 떨어지는가를 봄
for j in range(1, ma+1):
    if (j*mi) % ma == 0:
        lcm = (j*mi)
        break

print(gcd)
print(lcm)
```

### 비고
