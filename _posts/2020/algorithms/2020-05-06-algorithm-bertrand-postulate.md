---
title: "[Python] BOJ 4948번. 베르트랑 공준"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Silver2
meta_keywords: 알고리즘,백준,파이썬,4948번
date: 2020-05-06 23:30:00 -0400
---

# 4948번. 베르트랑 공준

### 문제 링크

- <https://www.acmicpc.net/problem/4948>{: target="\_blank"}

### 풀이 코드

```python
# 4948. 베르트랑 공준
primeList = [True for _ in range(270000)]

# true : 소수
primeList[0] = False
primeList[1] = False

for i in range(2, 270000):
    if primeList[i] == False:
        continue
    for j in range(i+i, 270000, i):
        primeList[j] = False  # i의 배수들을 다 false로 만들어줌

while True:
    n = int(input())
    if n == 0:
        break
    else:
        print(sum(primeList[n+1:2*n+1]))
```

### 비고

- 미리 리스트를 선언해야 시간 초과가 나지 않는다.
- i의 배수를 다 false로 지우면 쉽게 할 수 있다.
