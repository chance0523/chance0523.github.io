---
title: "[Python] BOJ 17219번. 비밀번호 찾기"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Implement, Silver4]
toc: true
toc_sticky: true
date: 2020-06-01 20:52:55 -0400
last_modified_at: 2020-06-01T20:52:55+08:00
---

# 17219번. 비밀번호 찾기

### 문제 링크
- <https://www.acmicpc.net/problem/17219>{: target="\_blank"}

### 풀이 코드

```python
# 17219번. 비밀번호 찾기


import sys
input = sys.stdin.readline

n, m = map(int, input().split())
# 딕셔너리를 이용해 url과 password가 바로 매칭 가능하게 함
upDict = {}
pList = [0 for i in range(m)]
for i in range(n):
    url, password = input().rstrip().split()
    upDict[url] = password
for i in range(m):
    url = input().rstrip()
    print(upDict[url])
```

### 비고