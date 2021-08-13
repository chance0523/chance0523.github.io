---
title: "[Python] BOJ 5525번. IOIOI"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-02 01:20:06 -0400
last_modified_at: 2020-06-02T01:20:06+08:00
---

# 5525번. IOIOI

### 문제 링크
- <https://www.acmicpc.net/problem/5525>{: target="\_blank"}

### 풀이 코드

```python
# 5525번. IOIOI


import sys
input = sys.stdin.readline
n = int(input())
m = int(input())
s = input().rstrip()

i = -1
cntO = 0
ans = 0
try:
    while i < m-2:
        i += 1
        if s[i] == 'I':
            cntO = 0
            while s[i+1] == 'O' and s[i+2] == 'I':
                cntO += 1
                i += 2
                if cntO == n:
                    cntO -= 1
                    ans += 1
                if i > m-2:
                    break
except:
    pass
print(ans)
```

### 비고