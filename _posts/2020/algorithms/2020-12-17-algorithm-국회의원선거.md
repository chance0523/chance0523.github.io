---
title: "[Python] BOJ 1417번. 국회의원 선거"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-12-17 18:26:55 -0400
last_modified_at: 2020-12-17T18:26:55+08:00
---

# 1417번. 국회의원 선거

### 문제 링크
- <https://www.acmicpc.net/problem/1417>{: target="\_blank"}

### 풀이 코드

```python
# 1417번. 국회의원 선거


n = int(input())
nList = [int(input()) for _ in range(n)]

da = nList[0]
nList.pop(0)
if n == 1:  # 런타임에러 방지
    print(0)
else:
    ans = 0
    while True:
        nList.sort()  # 계속 정렬해줌
        if da > nList[-1]:  # 다솜이의 값이 제일 클 때
            print(ans)
            break
        # 한 표를 넘겨받음
        nList[-1] -= 1
        da += 1
        ans += 1
```

### 비고