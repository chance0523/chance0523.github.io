---
title: "[Python] BOJ 1094번. 막대기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ math Silver5
meta_keywords: 알고리즘,백준,파이썬,1094번
date: 2021-01-14 19:20:25 -0400
last_modified_at: 2021-01-14T19:20:25+08:00
---

# 1094번. 막대기

### 문제 링크
- <https://www.acmicpc.net/problem/1094>{: target="\_blank"}

### 풀이 코드

```python
# 1094번. 막대기


x = int(input())
stick = [64]  # 처음엔 64cm짜리 하나만 들어있다.
while True:
    if sum(stick) == x:
        print(len(stick))
        break
    # 합이 x보다 크다면
    cur = stick.pop()
    stick.append(cur // 2)  # 반으로 나눠주기
    if sum(stick) < x:  # 길이가 작으면
        stick.append(cur // 2)  # 나머지 반도 포함
```

### 비고