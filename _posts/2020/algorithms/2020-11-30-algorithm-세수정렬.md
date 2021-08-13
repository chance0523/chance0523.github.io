---
title: "[Python] BOJ 2752번. 세수정렬"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-11-30 04:41:53 -0400
last_modified_at: 2020-11-30T04:41:53+08:00
---

# 2752번. 세수정렬

### 문제 링크
- <https://www.acmicpc.net/problem/2752>{: target="\_blank"}

### 풀이 코드

```python
# 2752번. 세수정렬


nList = list(map(int, input().split()))
nList.sort()
print(nList[0], nList[1], nList[2])
```

### 비고