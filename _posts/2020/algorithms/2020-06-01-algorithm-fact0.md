---
title: '[Python] BOJ 1676번. 팩토리얼 0의 개수'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Implement, Silver3]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,1676번
date: 2020-06-01 20:57:49 -0400
last_modified_at: 2020-06-01T20:57:49+08:00
---

# 1676번. 팩토리얼 0의 개수

### 문제 링크

-   <https://www.acmicpc.net/problem/1676>{: target="\_blank"}

### 풀이 코드

```python
# 1676번. 팩토리얼 0의 개수


import sys
input = sys.stdin.readline

n = int(input())

f = 1
for i in range(1, n+1):
    f *= i
# 숫자를 한 자리 한 자리
# 리스트 형태로 만들어줘서 맨 뒤부터 체크
f = list(str(f))

ans = 0
for i in range(len(f)-1, -1, -1):
    if f[i] == '0':
        ans += 1
    else:
        break
print(ans)
```

### 비고
