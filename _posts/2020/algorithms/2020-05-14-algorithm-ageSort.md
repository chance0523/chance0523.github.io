---
title: "[Python] BOJ 10814번. 나이순 정렬"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ sort Silver5
meta_keywords: 알고리즘,백준,파이썬,10814번
date: 2020-05-14 02:07:17 -0400
last_modified_at: 2020-05-14T02:07:17+08:00
---

# 10814번. 나이순 정렬

### 문제 링크

- <https://www.acmicpc.net/problem/10814>{: target="\_blank"}

### 풀이 코드

```python
# 10814번. 나이순 정렬

n = int(input())
userList = []
for i in range(n):
    age, name = input().split()
    # 몇 번째 들어왔는지도 확인
    userList.append((int(age), i, name))

userList.sort()

for age, i, name in userList:
    print(age, name)
```

### 비고
