---
title: "[Python] BOJ 1912번. 연속합"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, DP, Silver2]
toc: true
toc_sticky: true
date: 2020-06-09 21:12:45 -0400
last_modified_at: 2020-06-09T21:12:45+08:00
---

# 1912번. 연속합

### 문제 링크
- <https://www.acmicpc.net/problem/1912>{: target="\_blank"}

### 풀이 코드

```python
# 1912번. 연속합


n = int(input())
nList = list(map(int, input().split()))

sum = [nList[0]]
for i in range(n-1):
    sum.append(max(sum[i]+nList[i+1], nList[i+1]))
print(max(sum))
```

### 비고