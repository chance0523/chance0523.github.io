---
title: '[Python] BOJ 18301번. Rats'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-22 02:58:12 -0400
last_modified_at: 2020-05-22T02:58:12+08:00
---

# 18301번. Rats

### 문제 링크

-   <https://www.acmicpc.net/problem/18301>{: target="\_blank"}

### 풀이 코드

```python
# 18301번. Rats


a, b, c = map(int, input().split())

print(int(((a+1)*(b+1))/(c+1)-1))
```

### 비고
