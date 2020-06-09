---
title: "[Python] BOJ 1002번. 터렛"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ geometry Silver4
meta_keywords: 알고리즘,백준,파이썬,1002번
date: 2020-06-09 21:03:49 -0400
last_modified_at: 2020-06-09T21:03:49+08:00
---

# 1002번. 터렛

### 문제 링크
- <https://www.acmicpc.net/problem/1002>{: target="\_blank"}

### 풀이 코드

```python
# 1002번. 터렛


t = int(input())

for i in range(t):
    x1, y1, r1, x2, y2, r2 = map(int, input().split())
    dis = ((x1-x2)**2+(y1-y2)**2)**0.5  # 두 점 사이의 거리

    # 두 점이 같은 점이면
    if dis == 0:
        if r1 == r2:
            print(-1)
        else:
            print(0)
    else:
        # 외접, 내접
        if dis == r1+r2 or dis == abs(r1-r2):
            print(1)
        elif dis > r1+r2 or dis < abs(r1-r2):
            print(0)
        else:
            print(2)
```

### 비고