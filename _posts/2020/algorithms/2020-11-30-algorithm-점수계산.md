---
title: "[Python] BOJ 2822번. 점수 계산"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-11-30 05:22:05 -0400
last_modified_at: 2020-11-30T05:22:05+08:00
---

# 2822번. 점수 계산

### 문제 링크
- <https://www.acmicpc.net/problem/2822>{: target="\_blank"}

### 풀이 코드

```python
# 2822번. 점수 계산


import sys
input = sys.stdin.readline

# 입력 8개줄
nList = []
for i in range(1, 9):
    nList.append([int(input()), i])
nList.sort(reverse=True)
ans = 0

for i in range(5):
    ans += nList[i][0]
print(ans)  # 합 출력

ansList = []  # 문제 출력
for i in range(5):
    ansList.append(nList[i][1])
ansList.sort()  # 문제 번호 증가하는 순서
print(*ansList)  # 출력 형식 맞춰서
```

### 비고