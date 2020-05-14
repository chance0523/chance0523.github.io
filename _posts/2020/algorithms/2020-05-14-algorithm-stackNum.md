---
title: "[Python] BOJ 1874번. 스택 수열"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ stack Silver3
meta_keywords: 알고리즘,백준,파이썬,1874번
date: 2020-05-14 23:57:51 -0400
last_modified_at: 2020-05-14T23:57:51+08:00
---

# 1874번. 스택 수열

### 문제 링크
- <https://www.acmicpc.net/problem/1874>{: target="\_blank"}

### 풀이 코드

```python
# 1874번. 스택 수열import sys
input = sys.stdin.readline

n = int(input())

stack = []
op = []
cnt = 1
flag = True

# 4,3,6,8,7,5,2,1
for i in range(n):
    num = int(input())
    while cnt <= num:
        # 1,2,3,4를 담는다
        stack.append(cnt)
        op.append('+')
        cnt += 1
    if stack[-1] == num:
        # 4,3을 pop
        stack.pop()
        op.append('-')
    else:
        flag = False
if flag == False:
    print('NO')
else:
    for i in op:
        print(i)
```

### 비고