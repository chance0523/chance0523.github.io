---
title: '[Python] programmers 소수 찾기'
excerpt: ''
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-13 19:40:00 -0400
last_modified_at: 2020-05-13T19:40:00+08:00
---

# 완전탐색 | 소수 찾기

### 문제 링크

-   <https://programmers.co.kr/learn/courses/30/lessons/42839>{: target="\_blank"}

### 풀이 코드

```python
# 소수 찾기

from itertools import permutations


def primeList(n):
    primeList=[True]*n

    # i=sqrt(maximum)까지 검사
    m=int(n**0.5)

    for i in range(2,m+1):
        if primeList[i]==True:
            for j in range(i+i,n,i):
                primeList[j]=False
    return [i for i in range(2,n) if primeList[i]==True]

def solution(numbers):
    answer = 0
    numList=list(numbers)
    for i in range(2,len(numbers)+1):
        pm = list(permutations(numbers,i))
        for j in pm:
            if len(j)<=len(numbers):
                numList.append(''.join(j))

    # 정수형으로 바꿔주고, set으로 중복 제거
    numList = list(set([int(r) for r in numList]))

    if numList.count(1):
        numList.remove(1)
    if numList.count(0):
        numList.remove(0)

    primeL = primeList(max(numList)+1)
    for i in numList:
        if i in primeL:
            answer+=1

    return answer
```

### 비고
