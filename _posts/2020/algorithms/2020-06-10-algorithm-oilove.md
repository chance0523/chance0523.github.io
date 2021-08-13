---
title: "[Python] BOJ 16480번. 외심과 내심은 사랑입니다"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-10 01:29:08 -0400
last_modified_at: 2020-06-10T01:29:08+08:00
---

# 16480번. 외심과 내심은 사랑입니다

### 문제 링크
- <https://www.acmicpc.net/problem/16480>{: target="\_blank"}

### 풀이 코드

```python
# 16480번. 외심과 내심은 사랑입니다


# https://librewiki.net/wiki/%EC%99%B8%EC%8B%AC
R, r = map(int, input().split())

print((R*(R-2*r)))
```

### 비고