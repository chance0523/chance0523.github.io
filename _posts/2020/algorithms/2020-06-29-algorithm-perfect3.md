---
title: "[Python] BOJ 4690번. 완전 세제곱"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ implement Bronze
meta_keywords: 알고리즘,백준,파이썬,4690번
date: 2020-06-29 20:02:02 -0400
last_modified_at: 2020-06-29T20:02:02+08:00
---

# 4690번. 완전 세제곱

### 문제 링크
- <https://www.acmicpc.net/problem/4690>{: target="\_blank"}

### 풀이 코드

```python
# 4690번. 완전 세제곱


# a <= 100
# b,c,d <= 100
aList = [i**3 for i in range(101)]
ansList = []
for b in range(2, 101):
    for c in range(b, 101):
        for d in range(c, 101):
            a3 = b**3+c**3+d**3
            if a3 in aList:
                # print(a3, b, c, d)
                ansList.append([aList.index(a3), b, c, d])
ansList.sort()

for i in range(len(ansList)):
    print(
        f"Cube = {ansList[i][0]}, Triple = ({ansList[i][1]},{ansList[i][2]},{ansList[i][3]})")
```

### 비고