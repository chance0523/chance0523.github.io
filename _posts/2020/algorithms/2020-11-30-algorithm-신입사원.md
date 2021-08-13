---
title: "[Python] BOJ 1946번. 신입사원"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-11-30 03:56:15 -0400
last_modified_at: 2020-11-30T03:56:15+08:00
---

# 1946번. 신입사원

### 문제 링크
- <https://www.acmicpc.net/problem/1946>{: target="\_blank"}

### 풀이 코드

```python
# 1946번. 신입사원


import sys
input = sys.stdin.readline

for _ in range(int(input())):
    n = int(input())
    nList = [0 for i in range(n+1)]
    for i in range(n):
        s, m = map(int, input().split())  # '순위' (1~n등)
        # 서류와 면접 성적이 '모두' 떨어지면 선발 X
        nList[s] = m  # 이렇게 넣으면 서류 1~n등 순으로 들어감

    # 초기값 설정
    curMin = nList[1]  # 현재 커트라인의 기준치
    ans = 1
    # 면접 순위만 비교하면 된다
    for i in range(2, n + 1):  # 2번째부터 n번째까지
        if curMin >= nList[i]:  # 커트라인 올리기
            curMin = nList[i]
            ans += 1
    print(ans)
```

### 비고