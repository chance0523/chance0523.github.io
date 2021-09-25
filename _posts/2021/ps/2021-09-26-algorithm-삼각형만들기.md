---
title: '[Python] BOJ 1448번. 삼각형 만들기'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-09-26 11:10:25 -0400
last_modified_at: 2021-09-26T11:10:25+08:00
---

# 1448번. 삼각형 만들기

### 문제 링크
- <https://www.acmicpc.net/problem/1448>{: target="\_blank"}

### 풀이 코드
- 삼각형의 성질을 알고 있다면 쉽게 풀 수 있는 문제입니다.
- 변의 길이가 긴 순서대로 a,b,c라고 한다면, `a < b + c`를 만족해야 삼각형입니다.
- 이 성질을 이용하기 위해 내림차순으로 정렬을 하고 3개씩 비교해주면 됩니다.

```python
# 1448번. 삼각형 만들기


import sys
input = sys.stdin.readline

n = int(input())
nList = []
for i in range(n):
    nList.append(int(input()))

nList.sort(reverse=True)

for i in range(n-2):
    if nList[i] < nList[i+1] + nList[i+2]:
        print(nList[i] + nList[i+1] + nList[i+2])
        exit()
print(-1)
```

### 비고