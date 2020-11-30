---
title: "[Python] BOJ 18291번. 비요뜨의 징검다리 건너기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ math Silver1
meta_keywords: 알고리즘,백준,파이썬,18291번
date: 2020-07-24 00:21:04 -0400
last_modified_at: 2020-07-24T00:21:04+08:00
---

# 18291번. 비요뜨의 징검다리 건너기

### 문제 링크
- <https://www.acmicpc.net/problem/18291>{: target="\_blank"}

### 풀이 코드

```python
# 18291번. 비요뜨의 징검다리 건너기


for _ in range(int(input())):
    n = int(input())
    x = 2  # 2의 제곱
    n -= 2  # 2의 n-2제곱으로 풀어야함
    mod = 10**9+7
    ans = 1
    # 고속 거듭제곱
    if n < 0:
        print(1)
    else:
        while n:
            if n & 1:
                ans *= x
                ans %= mod
            n //= 2
            x *= x
            x %= mod
        print(ans)
```

### 비고