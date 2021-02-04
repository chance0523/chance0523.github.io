---
title: "[Python] BOJ 1016번. 제곱 ㄴㄴ 수"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Implement, Gold1]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,1016번
date: 2020-06-08 01:27:38 -0400
last_modified_at: 2020-06-08T01:27:38+08:00
---

# 1016번. 제곱 ㄴㄴ 수

### 문제 링크
- <https://www.acmicpc.net/problem/1016>{: target="\_blank"}

### 풀이 코드

```python
# 1016번. 제곱 ㄴㄴ 수


import math
import sys
input = sys.stdin.readline


mi, ma = map(int, input().split())

# min ~ max의 범위를 갖는 리스트
vList = [True for i in range(mi, ma+1)]

# max의 제곱근보다 작은 제곱수의 리스트
sList = [i**2 for i in range(2, int(ma**0.5)+1)]

# print(sList)
# 제곱수의 리스트에서 하나씩 뽑는다
for s in sList:
    # min ~ max의 수 중, 해당 제곱수의 최소의 배수를 구함
    # min값을 빼줌으로 vList의 index로 직접 사용
    idx = (math.ceil(mi/s)*s)-mi
    while idx <= ma-mi:
        # 제곱수의 배수이면 False로 바꿔줌
        vList[idx] = False
        # 다음 배수
        idx += s

# bool 리스트이므로 sum이 곧 True의 합
ans = sum(vList)
print(ans)
```

### 비고