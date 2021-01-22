---
title: "[Python] BOJ 2417번. 정수 제곱근"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ math Silver5
meta_keywords: 알고리즘,백준,파이썬,2417번
date: 2020-08-18 19:44:22 -0400
last_modified_at: 2020-08-18T19:44:22+08:00
---

# 2417번. 정수 제곱근

### 문제 링크
- <https://www.acmicpc.net/problem/2417>{: target="\_blank"}

### 풀이 코드

```python
# 2417번. 정수 제곱근


n = int(input())
tempRoot = n**0.5  # 제곱근

if(tempRoot-int(tempRoot) == 0):  # 정수라면
    print(int(tempRoot))

else:
    print(int(tempRoot)+1)
```

### 비고