---
title: '[Python] BOJ 10699번. 오늘 날짜'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Bronze]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,10699번
date: 2020-05-12 20:18:00 -0400
last_modified_at: 2020-05-12T20:18:00+08:00
---

# 10699번. 오늘 날짜

### 문제 링크

-   <https://www.acmicpc.net/problem/10699>{: target="\_blank"}

### 풀이 코드

~~아래 무슨 말 때문에 계속 uct 쓰다 실패...~~

```python
# 10699번. 오늘 날짜

from datetime import datetime

print(str(datetime.now())[:10])
```

### 비고

-   브론즈5
