---
title: "[Python] BOJ 1025번. 제곱수 찾기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ bruteforcing Silver1
meta_keywords: 알고리즘,백준,파이썬,1025번
date: 2020-05-14 00:17:08 -0400
last_modified_at: 2020-05-14T00:17:08+08:00
---

# 1025번. 제곱수 찾기

### 문제 링크

- <https://www.acmicpc.net/problem/1025>{: target="\_blank"}

### 풀이 코드

```python
# 1025번. 제곱수 찾기

import math

N, M = map(int, input().split())
box = [[0 for _ in range(M)] for _ in range(N)]
for i in range(N):
    box[i] = list(map(int, input()))

result = -1

for n in range(N):
    for m in range(M):
        for weight_n in range(-N, N):
            for weight_m in range(-M, M):
                if weight_n == 0 and weight_m == 0:
                    continue
                step = 0
                x = n
                y = m
                value = ''

                while(0 <= x < N) and (0 <= y < M):
                    value += str(box[x][y])
                    step += 1
                    value_int = int(''.join(value))
                    value_sqrt = math.sqrt(value_int)
                    value_decimal = value_sqrt - int(value_sqrt)
                    if value_decimal == 0 and value_int > result:
                        result = value_int

                    x = n + step * weight_n
                    y = m + step * weight_m
print(result)

```

### 비고
