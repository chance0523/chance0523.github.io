---
title: "[Python] BOJ 2869번. 달팽이는 올라가고 싶다"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Bronze
meta_keywords: 알고리즘,백준,파이썬,2869번
date: 2020-05-14 15:46:10 -0400
last_modified_at: 2020-05-14T15:46:10+08:00
---

# 2869번. 달팽이는 올라가고 싶다

### 문제 링크

- <https://www.acmicpc.net/problem/2869>{: target="\_blank"}

### 풀이 코드

```python
# 2869번. 달팽이는 올라가고 싶다

a, b, v = map(int, input().split())

m = 0
if (v-b) % (a-b) == 0:
    m = (v-b)//(a-b)
else:
    m = ((v-b)//(a-b))+1
print(m)
```

### 비고
