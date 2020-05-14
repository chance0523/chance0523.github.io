---
title: "[Python] BOJ 2775번. 부녀회장이 될테야"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Bronze
meta_keywords: 알고리즘,백준,파이썬,2775번
date: 2020-05-14 15:27:32 -0400
last_modified_at: 2020-05-14T15:27:32+08:00
---

# 2775번. 부녀회장이 될테야

### 문제 링크
- <https://www.acmicpc.net/problem/2775>{: target="\_blank"}

### 풀이 코드

```python
# 2775번. 부녀회장이 될테야t = int(input())

apart = [[0 for _ in range(14)] for _ in range(15)]
apart[0] = [i for i in range(1, 15)]
for a in range(1, 15):
    for b in range(14):
        apart[a][b] = sum(apart[a-1][:b+1])

for _ in range(t):
    k = int(input())
    n = int(input())
    print(apart[k][n-1])
```

### 비고