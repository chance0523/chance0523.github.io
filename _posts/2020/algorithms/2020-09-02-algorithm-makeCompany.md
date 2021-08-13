---
title: "[Python] BOJ 16890번. 창업"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-09-02 00:14:49 -0400
last_modified_at: 2020-09-02T00:14:49+08:00
---

# 16890번. 창업

### 문제 링크
- <https://www.acmicpc.net/problem/16890>{: target="\_blank"}

### 풀이 코드

```python
# 16890번. 창업


import sys
input = sys.stdin.readline


k = list(input().rstrip())
c = list(input().rstrip())
n = len(k)
ans = ['?' for i in range(n)]

k.sort()
c.sort(reverse=True)


turn = True
af = 0  # ans의 앞
ae = n-1  # 지금 ans의 맨 뒤에 넣으면 들어가는 곳
kf = 0  # k의 앞
ke = (n+1)//2-1  # k의 뒤
cf = 0  # c의 앞
ce = n//2-1  # c의 뒤

for i in range(n):
    if turn:
        # koo
        if k[kf] < c[cf]:  # 그냥 넣을 수 있음
            ans[af] = k[kf]
            af += 1
            kf += 1
        else:  # 뒤에서 빼서 뒤에 넣는게 낫다
            ans[ae] = k[ke]
            ae -= 1  # 뒤에 넣을 것을 줄여줌
            ke -= 1
    else:
        # cube
        if k[kf] < c[cf]:  # 그냥 넣을 수 있음
            ans[af] = c[cf]
            af += 1
            cf += 1
        else:
            ans[ae] = c[ce]
            ae -= 1
            ce -= 1
    turn = not turn

print(''.join(ans))
```

### 비고