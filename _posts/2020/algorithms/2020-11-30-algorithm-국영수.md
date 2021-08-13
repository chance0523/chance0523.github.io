---
title: "[Python] BOJ 10825번. 국영수"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-11-30 04:50:03 -0400
last_modified_at: 2020-11-30T04:50:03+08:00
---

# 10825번. 국영수

### 문제 링크
- <https://www.acmicpc.net/problem/10825>{: target="\_blank"}

### 풀이 코드

```python
# 10825번. 국영수


import sys
input = sys.stdin.readline

# 자바로 다시 풀어봄직한 문제이다.
n = int(input())
nList = []
for i in range(n):
    name, kor, eng, math = input().split()
    kor = -int(kor)  # 감소하는 순서로 넣기 위함
    eng = int(eng)
    math = -int(math)  # 감소하는 순서로 넣기 위함
    nList.append([kor, eng, math, name])

nList.sort()  # 정렬

for p in nList:
    print(p[-1])  # 이름만 출력
```

### 비고