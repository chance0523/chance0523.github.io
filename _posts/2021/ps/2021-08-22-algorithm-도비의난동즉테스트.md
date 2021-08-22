---
title: '[Python] BOJ 2204번. 도비의 난독증 테스트'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-08-22 10:45:25 -0400
last_modified_at: 2021-08-22T10:45:25+08:00
---

# 2204번. 도비의 난독증 테스트

### 문제 링크
- <https://www.acmicpc.net/problem/2204>{: target="\_blank"}

### 풀이 코드
- 간단한 정렬문제입니다.
- 파이썬의 lower()를 통해서 소문자로 변환해주면 비교가 가능한데, 리스트에 [소문자로 변환한 것, 기존 문자열] 이런식으로 넣어주고 정렬하면 기존의 문자열도 들고 있을 수 있습니다.

```python
# 2204번. 도비의 난독증 테스트


while True:
    n = int(input())
    if n == 0:
        break
    sList = []
    for _ in range(n):
        s = input().rstrip()
        sList.append([s.lower(), s])
    sList.sort()
    print(sList[0][1])
```

### 비고