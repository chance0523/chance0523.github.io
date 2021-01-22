---
title: "[Python] BOJ 1076번. 저항"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ math Bronze
meta_keywords: 알고리즘,백준,파이썬,1076번
date: 2020-07-17 21:04:23 -0400
last_modified_at: 2020-07-17T21:04:23+08:00
---

# 1076번. 저항

### 문제 링크
- <https://www.acmicpc.net/problem/1076>{: target="\_blank"}

### 풀이 코드

```python
# 1076번. 저항


rDict = {
    'black': 0,
    'brown': 1,
    'red': 2,
    'orange': 3,
    'yellow': 4,
    'green': 5,
    'blue': 6,
    'violet': 7,
    'grey': 8,
    'white': 9
}

a1 = input()
a2 = input()
a3 = input()
ans = (rDict[a1]*10+rDict[a2])*(10**rDict[a3])
print(ans)
```

### 비고