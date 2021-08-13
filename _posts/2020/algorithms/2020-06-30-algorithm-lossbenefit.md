---
title: "[Python] BOJ 1712번. 손익분기점"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-30 07:32:08 -0400
last_modified_at: 2020-06-30T07:32:08+08:00
---

# 1712번. 손익분기점

### 문제 링크
- <https://www.acmicpc.net/problem/1712>{: target="\_blank"}

### 풀이 코드

```python
# 1712번. 손익분기점


a, b, c = map(int, input().split())

if c <= b:
    ans = -1
else:
    ans = a//(c-b) + 1
print(ans)
```

### 비고