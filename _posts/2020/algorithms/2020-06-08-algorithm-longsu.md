---
title: "[Python] BOJ 11053번. 가장 긴 증가하는 부분 수열"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ DP Silver2
meta_keywords: 알고리즘,백준,파이썬,11053번
date: 2020-06-08 19:18:06 -0400
last_modified_at: 2020-06-08T19:18:06+08:00
---

# 11053번. 가장 긴 증가하는 부분 수열

### 문제 링크
- <https://www.acmicpc.net/problem/11053>{: target="\_blank"}

### 풀이 코드

```python
# 11053번. 가장 긴 증가하는 부분 수열


a = int(input())
aList = list(map(int, input().split()))

dp = [1 for i in range(a)]
for i in range(a):
    for j in range(i+1):
        if aList[j] < aList[i]:
            dp[i] = max(dp[i], dp[j]+1)
print(max(dp))
```

### 비고