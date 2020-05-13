---
title: "[Python] BOJ 3003번. 킹, 퀸, 룩, 비숍, 나이트, 폰"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Bronze5
meta_keywords: 알고리즘,백준,파이썬,3003번
date: 2020-05-12 12:48:00 -0400
last_modified_at: 2020-05-12T12:48:00+08:00
---

# 3003번. 킹, 퀸, 룩, 비숍, 나이트, 폰

### 문제 링크

- <https://www.acmicpc.net/problem/3003>{: target="\_blank"}

### 풀이 코드

```python
# 3003번. 킹, 퀸, 룩, 비숍, 나이트, 폰

king, queen, rook, bishop, knight, pawn = map(int, input().split(' '))
# 1,1,2,2,2,8
print(1-king, 1-queen, 2-rook, 2-bishop, 2-knight, 8-pawn)
```

### 비고

- 브론즈5
