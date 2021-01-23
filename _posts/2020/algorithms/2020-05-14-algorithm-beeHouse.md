---
title: '[Python] BOJ 2292번. 벌집'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, Bronze]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,2292번
date: 2020-05-14 15:16:38 -0400
last_modified_at: 2020-05-14T15:16:38+08:00
---

# 2292번. 벌집

### 문제 링크

-   <https://www.acmicpc.net/problem/2292>{: target="\_blank"}

### 풀이 코드

```python
# 2292번. 벌집

# 1 : 1
# 2 ~ 7 : 6
# 8 ~ 19 : 12
# 20 ~ 37 : 18
# 6개씩 증가한다

n = int(input())
start = 1
p = 6
num = 1
if n == 1:
    print(1)
else:
    while True:
        start += p
        num += 1
        if n <= start:
            print(num)
            break
        p += 6
```

### 비고
