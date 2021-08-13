---
title: "[Python] BOJ 1026번. 보물"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-11 12:29:27 -0400
last_modified_at: 2020-06-11T12:29:27+08:00
---

# 1026번. 보물

### 문제 링크
- <https://www.acmicpc.net/problem/1026>{: target="\_blank"}

### 풀이 코드

```python
# 1026번. 보물


n = int(input())
aList = list(map(int, input().split()))
bList = list(map(int, input().split()))

# aList에서 큰 것들은 bList에서 작은 것들과
# 작은 것들은 큰 것들과 매칭
aList.sort(reverse=True)
bList.sort()

s = 0
for i in range(n):
    s += (aList[i]*bList[i])
print(s)
```

### 비고