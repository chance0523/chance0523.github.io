---
title: "[Python] BOJ 1038번. 감소하는 수"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ brute_force_search Gold5
meta_keywords: 알고리즘,백준,파이썬,1038번
date: 2020-05-14 01:04:43 -0400
last_modified_at: 2020-05-14T01:04:43+08:00
---

# 1038번. 감소하는 수

### 문제 링크
- <https://www.acmicpc.net/problem/1038>{: target="\_blank"}

### 풀이 코드

```python
# 1038번. 감소하는 수
dList = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
a = 10
for d in dList:
    t = d % a
    if d != 0 and d != 1:
        for i in range(t):
            dList.append((d*10+i))

n = int(input())
if n < len(dList):
    print(dList[n])
else:
    print(-1)
```

### 비고