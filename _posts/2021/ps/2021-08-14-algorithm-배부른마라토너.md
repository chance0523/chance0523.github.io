---
title: '[Python] BOJ 10546번. 배부른 마라토너'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-08-14 11:55:25 -0400
last_modified_at: 2021-08-14T11:55:25+08:00
---

# 10546번. 배부른 마라토너

### 문제 링크
- <https://www.acmicpc.net/problem/10546>{: target="\_blank"}

### 풀이 코드
- n을 보고 완탐으로 풀면 안되겠다는 생각을 가지면 되는 문제입니다.
- 동명이인이 있을수 있다만 주의해서 풀어주면 됩니다.

```python
# 10546번. 배부른 마라토너


import sys
input = sys.stdin.readline

n = int(input().rstrip())
sDict = {}
for i in range(n):
    s = input().rstrip()
    if s not in sDict:
        sDict[s] = 1
    else: # 동명이인 가능
        sDict[s] += 1

for i in range(n-1):
    s = input().rstrip()
    sDict[s] -= 1 # 완주한 이름은 -1

for key, value in sDict.items():
    if value != 0: # 아직 남아있다면
        print(key)
        break
```

### 비고