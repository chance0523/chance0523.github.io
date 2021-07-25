---
title: '[Python] BOJ 5489번. Numbers'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬,5489번]
toc: true
toc_sticky: true
date: 2021-07-24 19:20:25 -0400
last_modified_at: 2021-07-24T19:20:25+08:00
---

# 5489번. Numbers

### 문제 링크
- <https://www.acmicpc.net/problem/5489>{: target="\_blank"}

### 풀이 코드

- 가장 많이 나온 수들 중 가장 작은 수를 고르는 문제입니다.
- brute force로 풀 수 있겠지만, 뭔가 정렬로 세련되게 풀 수 있어보입니다.
- 리스트를 크게 선언해주고 '[나온횟수, 숫자]' 다음과 같이 넣고 정렬하면 될 것 같아보입니다.
- 그냥 `sort()`로 정렬하면 나온 횟수가 적은 순서로 정렬되기에 넣을 때부터 `-=1`을 하여 [나온횟수(음수), 숫자]로 하여 sort()하면 됩니다. Easy~


```python
# 5489번. Numbers


n = int(input())
nList = [[0, i] for i in range(100001)]
for i in range(n):
    x = int(input())
    nList[x][0]-=1

nList.sort()
print(nList[0][1])
```

### 비고