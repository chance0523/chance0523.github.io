---
title: "[Python] BOJ 10815번. 숫자 카드"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-11 12:22:41 -0400
last_modified_at: 2020-06-11T12:22:41+08:00
---

# 10815번. 숫자 카드

### 문제 링크
- <https://www.acmicpc.net/problem/10815>{: target="\_blank"}

### 풀이 코드

```python
# 10815번. 숫자 카드


import sys
input = sys.stdin.readline

n = int(input())
cset = set(map(int, input().split()))
m = int(input())
nList = list(map(int, input().split()))


for i in range(m):
    if nList[i] in cset:
        print(1, end=' ')
    else:
        print(0, end=' ')
```

### 비고