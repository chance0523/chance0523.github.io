---
title: '[Python] BOJ 17256번. 달달함이 넘쳐흘러'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, Bronze]
toc: true
toc_sticky: true
date: 2020-05-22 02:42:45 -0400
last_modified_at: 2020-05-22T02:42:45+08:00
---

# 17256번. 달달함이 넘쳐흘러

### 문제 링크

-   <https://www.acmicpc.net/problem/17256>{: target="\_blank"}

### 풀이 코드

```python
# 17256번. 달달함이 넘쳐흘러


a = list(map(int, input().split()))
c = list(map(int, input().split()))

print(c[0]-a[2], c[1]//a[1], c[2]-a[0])
```

### 비고
