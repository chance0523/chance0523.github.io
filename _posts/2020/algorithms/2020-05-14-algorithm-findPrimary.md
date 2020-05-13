---
title: "[Python] BOJ 1978번. 소수 찾기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Silver4
meta_keywords: 알고리즘,백준,파이썬,1978번
date: 2020-05-14 02:31:33 -0400
last_modified_at: 2020-05-14T02:31:33+08:00
---

# 1978번. 소수 찾기

### 문제 링크
- <https://www.acmicpc.net/problem/1978>{: target="\_blank"}

### 풀이 코드

```python
# 1978번. 소수 찾기n = int(input())
nList = list(map(int, input().split()))

m = 1000

# 소수 리스트 만들기
def p(m):
    pList = [True]*m

    k = int(m**0.5)
    for i in range(2, k):
        if pList[i]:
            for j in range(i+i, m, i):
                pList[j] = False
    return [i for i in range(2, m) if pList[i]]


answer = 0
pList = p(m)
for num in nList:
    if num in pList:
        answer += 1
print(answer)
```

### 비고