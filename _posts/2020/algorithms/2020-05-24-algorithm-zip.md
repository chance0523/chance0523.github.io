---
title: '[Python] BOJ 18870번. 좌표 압축'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 구현, Silver2]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,18870번
date: 2020-05-24 01:12:25 -0400
last_modified_at: 2020-05-24T01:12:25+08:00
---

# 18870번. 좌표 압축

### 문제 링크

-   <https://www.acmicpc.net/problem/18870>{: target="\_blank"}

### 풀이 코드

```python
# 18870번. 좌표 압축


import sys
input = sys.stdin.readline

n = int(input())
nList = list(map(int, input().split()))

# set으로 중복 제거한 후 list로 만들어서 sort
nListS = sorted(list(set(nList)))

# nListS의 index가 곧 압축 결과이므로
# 편하게 dictionary로 계산
nDict = {}
for i in range(len(nListS)):
    nDict[nListS[i]] = i

for num in nList:
    print(nDict[num], end=' ')
```

### 비고
