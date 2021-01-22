---
title: "[Python] BOJ 1059번. 좋은구간"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ math Silver5
meta_keywords: 알고리즘,백준,파이썬,1059번
date: 2020-12-29 00:48:32 -0400
last_modified_at: 2020-12-29T00:48:32+08:00
---

# 1059번. 좋은구간

### 문제 링크
- <https://www.acmicpc.net/problem/1059>{: target="\_blank"}

### 풀이 코드

```python
# 1059번. 좋은구간


l = int(input())
sList = list(map(int, input().split()))
n = int(input())
sList.insert(0, 0)  # 0 ~ sList[0] 구간을 만들어줘야한다.
sList.sort()

if n in sList:  # 구간을 만들 수 없음
    print(0)
else:
    for i in range(l):
        if sList[i] < n < sList[i + 1]:  # 이 두 숫자 사이에 있다면
            # 구간 개수 계산
            # n보다 작거나 같은 수 x n보다 크거나 같은수 - 1
            ans = (n - sList[i]) * (sList[i + 1] - n) - 1
            print(ans)
            break
```

### 비고