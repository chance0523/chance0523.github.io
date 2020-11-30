---
title: "[Python] BOJ 11509번. 풍선 맞추기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ greedy Silver1
meta_keywords: 알고리즘,백준,파이썬,11509번
date: 2020-07-05 00:59:13 -0400
last_modified_at: 2020-07-05T00:59:13+08:00
---

# 11509번. 풍선 맞추기

### 문제 링크
- <https://www.acmicpc.net/problem/11509>{: target="\_blank"}

### 풀이 코드

```python
# 11509번. 풍선 맞추기


import sys
input = sys.stdin.readline

N = int(input())
nList = list(map(int, input().split()))
# 이 높이에서 날아오는 화살이 있나 check
arrow = [0 for height in range(1000001)]
ans = 0

for n in nList:
    # n+1 높이에서 날아오는 화살이 없는 경우
    if arrow[n+1] == 0:
        # n 높이에서 날아오는 화살 추가
        arrow[n] += 1
        ans += 1
    # n+1 높이에서 날아오는 화살이 있는 경우
    else:
        # n 높이로 교체
        arrow[n+1] -= 1
        arrow[n] += 1
print(ans)
```

### 비고