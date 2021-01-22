---
title: "[Python] BOJ 5622번. 다이얼"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ string Bronze
meta_keywords: 알고리즘,백준,파이썬,5622번
date: 2020-06-29 20:09:58 -0400
last_modified_at: 2020-06-29T20:09:58+08:00
---

# 5622번. 다이얼

### 문제 링크
- <https://www.acmicpc.net/problem/5622>{: target="\_blank"}

### 풀이 코드

```python
# 5622번. 다이얼


st = input().rstrip()
d = [3, 3, 3,
     4, 4, 4,
     5, 5, 5,
     6, 6, 6,
     7, 7, 7,
     8, 8, 8, 8,
     9, 9, 9,
     10, 10, 10, 10]
ans = 0
for s in st:
    num = ord(s)-ord('A')
    ans += d[num]
print(ans)
```

### 비고