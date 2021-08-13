---
title: "[Python] BOJ 1759번. 암호 만들기"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-09-07 15:50:25 -0400
last_modified_at: 2020-09-07T15:50:25+08:00
---

# 1759번. 암호 만들기

### 문제 링크
- <https://www.acmicpc.net/problem/1759>{: target="\_blank"}

### 풀이 코드

```python
# 1759번. 암호 만들기


from itertools import combinations
'''
4 6
a t c i s w
'''

l, c = map(int, input().split())
wList = list(input().split())
wList.sort()
cList = list(combinations(wList, l))

moList = ['a', 'e', 'i', 'o', 'u']

for c in cList:
    # 모음 개수
    mo = 0
    for m in moList:
        if m in c:
            mo += 1

    # 최소 한 개의 모음
    if mo == 0:
        continue
    # 최소 두 개의 자음
    if l - mo < 2:
        continue
    print(''.join(c))
```

### 비고