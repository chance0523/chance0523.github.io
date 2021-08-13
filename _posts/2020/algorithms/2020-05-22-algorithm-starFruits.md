---
title: '[Python] BOJ 17496번. 스타후르츠'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-22 02:46:37 -0400
last_modified_at: 2020-05-22T02:46:37+08:00
---

# 17496번. 스타후르츠

### 문제 링크

-   <https://www.acmicpc.net/problem/17496>{: target="\_blank"}

### 풀이 코드

```python
# 17496번. 스타후르츠


n, t, c, p = map(int, input().split())
# (n-1)//t -> 총 몇 번 수확 할 수 있는지
print(((n-1)//t)*c*p)
```

### 비고
