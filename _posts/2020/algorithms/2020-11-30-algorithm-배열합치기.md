---
title: "[Python] BOJ 11728번. 배열 합치기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ sort Silver5
meta_keywords: 알고리즘,백준,파이썬,11728번
date: 2020-11-30 05:15:10 -0400
last_modified_at: 2020-11-30T05:15:10+08:00
---

# 11728번. 배열 합치기

### 문제 링크
- <https://www.acmicpc.net/problem/11728>{: target="\_blank"}

### 풀이 코드

```python
# 11728번. 배열 합치기


import sys
input = sys.stdin.readline

n, m = map(int, input().split())
a = list(map(int, input().split()))
b = list(map(int, input().split()))
a.extend(b) # 그냥 한 리스트로 만들어주고
a.sort() # 정렬
print(*a) # 주어진 형식대로 출력
```

### 비고