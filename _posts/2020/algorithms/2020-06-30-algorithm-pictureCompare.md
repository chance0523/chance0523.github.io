---
title: "[Python] BOJ 2160번. 그림 비교"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-30 16:39:47 -0400
last_modified_at: 2020-06-30T16:39:47+08:00
---

# 2160번. 그림 비교

### 문제 링크
- <https://www.acmicpc.net/problem/2160>{: target="\_blank"}

### 풀이 코드

```python
# 2160번. 그림 비교


import sys
input = sys.stdin.readline

n = int(input())
picture = [[input().rstrip() for i in range(5)] for i in range(n)]
# print(picture)
ans = [35, 0, 0]
for i in range(n-1):
    for j in range(i+1, n):
        # 두 그림 비교
        cnt = 0
        for a in range(5):
            for b in range(7):
                if picture[i][a][b] != picture[j][a][b]:
                    cnt += 1
        if ans[0] > cnt:
            ans[0] = cnt
            ans[1] = i+1
            ans[2] = j+1
print(*ans[1:])
```

### 비고