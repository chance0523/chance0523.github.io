---
title: '[Python] BOJ 10773번. 제로'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, Silver4]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,10773번
date: 2020-05-14 22:58:39 -0400
last_modified_at: 2020-05-14T22:58:39+08:00
---

# 10773번. 제로

### 문제 링크

-   <https://www.acmicpc.net/problem/10773>{: target="\_blank"}

### 풀이 코드

```python
# 10773번. 제로

k = int(input())
stack = []
for i in range(k):
    num = int(input())
    if num != 0:
        stack.append(num)
    else:
        stack.pop()

print(sum(stack))
```

### 비고
