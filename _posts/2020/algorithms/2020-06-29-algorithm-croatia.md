---
title: "[Python] BOJ 2941번. 크로아티아 알파벳"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-29 20:42:30 -0400
last_modified_at: 2020-06-29T20:42:30+08:00
---

# 2941번. 크로아티아 알파벳

### 문제 링크
- <https://www.acmicpc.net/problem/2941>{: target="\_blank"}

### 풀이 코드

```python
# 2941번. 크로아티아 알파벳


s = input().rstrip()
ans = len(s)

ans -= s.count('c=')
ans -= s.count('c-')
ans -= s.count('dz=')
ans -= s.count('d-')
ans -= s.count('lj')
ans -= s.count('nj')
ans -= s.count('s=')
ans -= s.count('z=')

print(ans)
```

### 비고