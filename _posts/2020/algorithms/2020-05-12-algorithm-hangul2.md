---
title: "[Python] BOJ 11283번. 한글 2"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Bronze5
meta_keywords: 알고리즘,백준,파이썬,11283번
date: 2020-05-12 20:51:00 -0400
---

# 11283번. 한글 2

### 문제 링크

- <https://www.acmicpc.net/problem/11283>{: target="\_blank"}

### 풀이 코드

- ord() : 문자의 아스키 코드 값을 돌려줌
- '가'를 넣었을 때 44032
- 따라서 44031을 빼준다.

```python
# 11283번. 한글 2

print(ord(input())-44031)
```

### 비고

- 브론즈5
