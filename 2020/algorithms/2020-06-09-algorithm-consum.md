---
title: "[Python] BOJ 1912번. 연속합"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ DP Silver2
meta_keywords: 알고리즘,백준,파이썬,1912번
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