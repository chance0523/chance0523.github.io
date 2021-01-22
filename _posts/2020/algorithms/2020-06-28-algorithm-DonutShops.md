---
title: "[Python] codeforces edu90 A. Donut Shops"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm codeforces greedy implement
meta_keywords: 알고리즘,코드포스,파이썬
date: 2020-06-28 02:44:02 -0400
last_modified_at: 2020-06-28T02:44:02+08:00
---

# A. Donut Shops

### 문제 링크

- <https://codeforces.com/problemset/problem/1373/A>{: target="\_blank"}

### 풀이 코드

```python
# A. Donut Shops


import sys
input = sys.stdin.readline

t = int(input())
for i in range(t):
    # 1번 가게 : 하나에 a달러
    # 2번 가게 : b개에 c 달러 (하나에 c/b달러)
    a, b, c = map(int, input().split())

    if a >= c:
        # 1개만 사도 2번 가게가 더 싸다
        output1 = -1
        output2 = b
    else:  # a<c
        if a == (c/b):
            output1 = 1
            output2 = -1
        elif a < (c/b):
            output1 = 1
            output2 = -1
        else:  # a>(c/b)
            output1 = 1
            output2 = b
    print(output1, output2)
```

### 비고
