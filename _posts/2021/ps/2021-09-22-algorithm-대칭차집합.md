---
title: '[Python] BOJ 1269번. 대칭 차집합'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-09-22 11:35:25 -0400
last_modified_at: 2021-09-22T11:35:25+08:00
---

# 1269번. 대칭 차집합

### 문제 링크
- <https://www.acmicpc.net/problem/1269>{: target="\_blank"}

### 풀이 코드
- 파이썬의 `set` 자료구조를 통해 매우 쉽게 풀 수 있는 문제입니다.
- A - B와 B - A 모두 그대로 써주시면 됩니다. (`A-B == aSet - BSet`)
- 합집합은 `|`을 사용해주시면 됩니다.


```python
# 1269번. 대칭 차집합


a, b = map(int, input().split())
aSet = set(map(int, input().split()))
bSet = set(map(int, input().split()))
ab = aSet - bSet
ba = bSet - aSet
print(len(ab | ba))
```

### 비고