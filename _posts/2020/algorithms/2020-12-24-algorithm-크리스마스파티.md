---
title: "[Python] BOJ 10708번. 크리스마스 파티"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ implement Bronze
meta_keywords: 알고리즘,백준,파이썬,10708번
date: 2020-12-24 00:12:10 -0400
last_modified_at: 2020-12-24T00:12:10+08:00
---

# 10708번. 크리스마스 파티

### 문제 링크
- <https://www.acmicpc.net/problem/10708>{: target="\_blank"}

### 풀이 코드

```python
# 10708번. 크리스마스 파티


n = int(input())
m = int(input())
mList = list(map(int, input().split()))
friends = [0 for _ in range(n)]

for i in range(m):
    target = mList[i]
    nList = list(map(int, input().split()))
    for j in range(n):
        if nList[j] == target:  # 타겟을 맞췄으면
            friends[j] += 1
        else:  # 못 맞췄으면
            friends[target-1] += 1  # 인덱스 맞춰주기 위해
for i in range(n):
    print(friends[i])
```

### 비고