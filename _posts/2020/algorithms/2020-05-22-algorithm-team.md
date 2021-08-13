---
title: '[Python] BOJ 15727번. 조별과제를 하려는데 조장이 사라졌다'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, Bronze]
toc: true
toc_sticky: true
date: 2020-05-22 02:25:30 -0400
last_modified_at: 2020-05-22T02:25:30+08:00
---

# 15727번. 조별과제를 하려는데 조장이 사라졌다

### 문제 링크

-   <https://www.acmicpc.net/problem/15727>{: target="\_blank"}

### 풀이 코드

```python
# 15727번. 조별과제를 하려는데 조장이 사라졌다


l = int(input())

if l % 5:
    print(l//5+1)
else:
    print(l//5)
```

### 비고
