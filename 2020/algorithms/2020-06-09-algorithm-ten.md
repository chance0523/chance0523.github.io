---
title: "[Python] BOJ 11721번. 열 개씩 끊어 출력하기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Bronze
meta_keywords: 알고리즘,백준,파이썬,11721번
date: 2020-06-09 19:54:20 -0400
last_modified_at: 2020-06-09T19:54:20+08:00
---

# 11721번. 열 개씩 끊어 출력하기

### 문제 링크
- <https://www.acmicpc.net/problem/11721>{: target="\_blank"}

### 풀이 코드

```python
# 11721번. 열 개씩 끊어 출력하기


st = input()

i = 0
while True:
    # 열개씩 출력
    print(st[0+i:10+i])
    # 다음 10개로 이동
    i += 10
    # 만약에 다음 10개가 단어의 길이를 넘어서면
    if len(st) < 10+i:
        # 그냥 나머지만 출력하고 break
        print(st[0+i:])
        break
```

### 비고