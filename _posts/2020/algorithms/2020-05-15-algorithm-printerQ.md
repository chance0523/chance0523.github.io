---
title: "[Python] BOJ 1966번. 프린터 큐"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ stack Silver3
meta_keywords: 알고리즘,백준,파이썬,1966번
date: 2020-05-15 00:38:03 -0400
last_modified_at: 2020-05-15T00:38:03+08:00
---

# 1966번. 프린터 큐

### 문제 링크

- <https://www.acmicpc.net/problem/1966>{: target="\_blank"}

### 풀이 코드

```python
# 1966번. 프린터 큐

import sys
input = sys.stdin.readline

T = int(input())
for _ in range(T):
    n, m = map(int, input().split())
    paper = list(map(int, input().split()))
    imp = [0 for i in range(n)]
    imp[m] = 1
    cnt = 0
    while True:
        if paper[0] == max(paper):
            cnt += 1
            if imp[0] == 1:
                print(cnt)
                break
            else:
                paper.pop(0)
                imp.pop(0)
        else:
            # 맨 뒤에 넣어줌
            paper.append(paper.pop(0))
            imp.append(imp.pop(0))
```

### 비고
