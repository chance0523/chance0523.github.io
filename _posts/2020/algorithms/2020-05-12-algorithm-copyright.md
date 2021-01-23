---
title: '[Python] BOJ 2914번. 저작권'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Bronze5]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,2914번
date: 2020-05-12 12:44:00 -0400
last_modified_at: 2020-05-12T12:44:00+08:00
---

# 2914번. 저작권

### 문제 링크

-   <https://www.acmicpc.net/problem/2914>{: target="\_blank"}

### 풀이 코드

-   예제에 나온 A=38, I=24를 보자.
    I는 올림해서 24이므로 올림하기 전에는 23보다 크고 24보다 작거나 같다.
    23 < (멜로디 갯수 / 38) <= 24 를 만족하는 최소 멜로디 갯수는
    38\*23 + 1일 것이다.
-   이를 모든 수에 대해 코드로 구현하면 된다.

```python
# 2914번. 저작권

a, i = map(int, input().split(' '))
m = a*(i-1)+1
print(m)
```

### 비고

-   브론즈5
