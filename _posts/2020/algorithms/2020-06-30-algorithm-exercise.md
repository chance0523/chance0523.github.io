---
title: "[Python] BOJ 1173번. 운동"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-30 16:10:48 -0400
last_modified_at: 2020-06-30T16:10:48+08:00
---

# 1173번. 운동

### 문제 링크
- <https://www.acmicpc.net/problem/1173>{: target="\_blank"}

### 풀이 코드

```python
# 1173번. 운동


# 처음 맥박 m
# 운동을 하려고 하는 시간 N분
# 최대 맥박 M 최소 맥박 m
# 운동 시 T만큼 증가
# 휴식 시 R만큼 감소
N, m, M, T, R = map(int, input().split())
m_init = m
ans = 0
while True:
    # 운동을 할 수 없을 때.
    if m_init+T > M:
        print(-1)
        break
    # 운동
    if m+T <= M:
        m += T
        ans += 1
        N -= 1
    # 휴식
    else:
        ans += 1
        if m-R < m_init:
            m = m_init
        else:
            m -= R
    # 완료
    if N == 0:
        print(ans)
        break
```

### 비고