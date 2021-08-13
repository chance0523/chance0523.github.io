---
title: '[Python] Programmers. 소수 찾기'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,프로그래머스,파이썬,소수찾기]
toc: true
toc_sticky: true
date: 2021-08-13 21:30:25 -0400
last_modified_at: 2021-08-13T21:30:25+08:00
---

# 소수찾기

### 문제 링크
- <https://programmers.co.kr/learn/courses/30/lessons/12921>{: target="\_blank"}

### 풀이 코드
- 에라토스테네스의 체의 연습문제로 좋은 문제입니다.

```python
# 소수 찾기
def solution(n):
    answer = 0
    pList = [False for _ in range(n+1)]
    pList[0] = True 
    pList[1] = True # 0과 1은 소수가 아니다.
    for i in range(2,n+1):
        for j in range(i+i,n+1,i):
            pList[j] = True
    answer = pList.count(False) # 소수 세주기
    return answer
```

### 비고