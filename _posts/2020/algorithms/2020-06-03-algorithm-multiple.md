---
title: "[Python] BOJ 1629번. 곱셈"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Silver1
meta_keywords: 알고리즘,백준,파이썬,1629번
date: 2020-06-03 01:25:05 -0400
last_modified_at: 2020-06-03T01:25:05+08:00
---

# 1629번. 곱셈

### 문제 링크
- <https://www.acmicpc.net/problem/1629>{: target="\_blank"}

### 풀이 코드

```python
# 1629번. 곱셈


a, b, c = map(int, input().split())

# 이와 같은 일반적인 방법으로는 시간초과
# print(pow(a,b)%c)

# 이런 방법이 있다고 한다. 문제에서 설명한 그대로를 반환
print(pow(a, b, c))
```

### 비고