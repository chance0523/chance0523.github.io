---
title: '[Python] BOJ 2845번. 파티가 끝나고 난 뒤'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-22 02:06:27 -0400
last_modified_at: 2020-05-22T02:06:27+08:00
---

# 2845번. 파티가 끝나고 난 뒤

### 문제 링크

-   <https://www.acmicpc.net/problem/2845>{: target="\_blank"}

### 풀이 코드

```python
# 2845번. 파티가 끝나고 난 뒤


import sys
input = sys.stdin.readline

l, p = map(int, input().split())
a = list(map(int, input().split()))
san = l*p
for i in range(5):
    print(a[i]-san, end=' ')
```

### 비고
