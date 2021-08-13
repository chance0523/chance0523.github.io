---
title: "[Python] BOJ 4796번. 캠핑"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-12-19 02:00:41 -0400
last_modified_at: 2020-12-19T02:00:41+08:00
---

# 4796번. 캠핑

### 문제 링크
- <https://www.acmicpc.net/problem/4796>{: target="\_blank"}

### 풀이 코드

```python
# 4796번. 캠핑


import sys
input = sys.stdin.readline


cnt = 1
while True:
    l, p, v = map(int, input().split())
    if l == 0 and p == 0 and v == 0:  # 종료조건
        break
    ans = 0

    ans += (v // p)*l  # 이만큼의 덩어리들이 들어감
    remain = v - (v // p) * p  # 이만큼이 남음
    ans += min(remain, l)  # 남은 날짜와 p중에 더 작은 것을 더해줌

    print(f'Case {cnt}: {ans}')  # 출력
    cnt += 1
```

### 비고