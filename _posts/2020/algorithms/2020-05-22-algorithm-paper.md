---
title: '[Python] BOJ 2630번. 색종이 만들기'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-22 04:03:57 -0400
last_modified_at: 2020-05-22T04:03:57+08:00
---

# 2630번. 색종이 만들기

### 문제 링크

-   <https://www.acmicpc.net/problem/2630>{: target="\_blank"}

### 풀이 코드

```python
# 2630번. 색종이 만들기


n = int(input())

p = [0 for i in range(n)]

for i in range(n):
    p[i] = list(map(int, input().split()))

w_cnt, b_cnt = 0, 0


def div(x, y, n):
    global w_cnt, b_cnt
    cnt = 0
    for i in range(x, x+n):
        for j in range(y, y+n):
            if p[i][j]:
                cnt += 1
    if not cnt:
        w_cnt += 1
    elif cnt == n**2:
        b_cnt += 1
    else:
        div(x, y, n//2)  # 왼쪽위
        div(x+n//2, y, n//2)  # 왼쪽아래
        div(x, y+n//2, n//2)  # 오른쪽위
        div(x+n//2, y+n//2, n//2)  # 오른쪽아래
    return


div(0, 0, n)
print(w_cnt)
print(b_cnt)
```

### 비고
