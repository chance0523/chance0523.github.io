---
title: "[Python] BOJ 1439번. 뒤집기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ math Silver5
meta_keywords: 알고리즘,백준,파이썬,1439번
date: 2020-09-07 22:39:25 -0400
last_modified_at: 2020-09-07T22:39:25+08:00
---

# 1439번. 뒤집기

### 문제 링크
- <https://www.acmicpc.net/problem/1439>{: target="\_blank"}

### 풀이 코드

```python
# 1439번. 뒤집기


s = list(input())

one = 0
zero = 0
if s[0] == '0':
    zero += 1
else:
    one += 1
for i in range(1, len(s)):
    if s[i-1] != s[i]:
        if s[i] == '0':
            zero += 1
        else:
            one += 1

print(min(zero, one))
```

### 비고