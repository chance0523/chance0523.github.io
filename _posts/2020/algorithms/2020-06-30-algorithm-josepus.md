---
title: "[Python] BOJ 1158번. 요세푸스 문제"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-30 08:38:33 -0400
last_modified_at: 2020-06-30T08:38:33+08:00
---

# 1158번. 요세푸스 문제

### 문제 링크
- <https://www.acmicpc.net/problem/1158>{: target="\_blank"}

### 풀이 코드

```python
# 1158번. 요세푸스 문제


n, k = map(int, input().split())
nList = [i for i in range(1, n+1)]
ansList = []
idx = k-1
while True:
    ansList.append(nList.pop(idx))
    if not nList:
        break
    idx = (idx+k-1) % len(nList)
print('<'+', '.join(map(str, ansList))+'>')
```

### 비고