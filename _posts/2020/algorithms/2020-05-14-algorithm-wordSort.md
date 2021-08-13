---
title: '[Python] BOJ 1181번. 단어 정렬'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-14 01:35:05 -0400
last_modified_at: 2020-05-14T01:35:05+08:00
---

# 1181번. 단어 정렬

### 문제 링크

-   <https://www.acmicpc.net/problem/1181>{: target="\_blank"}

### 풀이 코드

```python
# 1181번. 단어 정렬

n = int(input())
wList = []
for i in range(n):
    wList.append(input())

wList = list(set(wList))  # 중복 제거

wListSort = []

# word length와 word를 한번에 저장
for w in wList:
    wListSort.append((len(w), w))

wListSort.sort()

for len_w, w in wListSort:
    print(w)
```

### 비고
