---
title: "[Python] BOJ 6118번. 숨바꼭질"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Graph Silver1
meta_keywords: 알고리즘,백준,파이썬,6118번
date: 2020-05-01 18:20:00 -0400
---

# 6118번. 숨바꼭질

### 문제 링크

- <https://www.acmicpc.net/problem/6118>{: target="\_blank"}

### 풀이 코드

```python
# 6118번. 숨바꼭질

n, m = map(int, input().split(' '))
s = [[] for _ in range(n+1)]

for i in range(m):
    a, b = map(int, input().split(' '))
    s[a].append(b)
    s[b].append(a)

start = 1  # 시작 헛간
visited = [0]*(n+1)
visited[start] = 1

d = 0  # 거리
now = [start]

while True:
    nxt = []
    # nxt에 start로부터 거리가 같은 헛간을 넣어주고
    # visited에 check
    for i in now:
        for j in s[i]:
            if visited[j] == 1:
                continue
            else:
                nxt.append(j)
                visited[j] = 1
    if nxt:
        now = nxt
        d += 1
    else:
        print(min(now), d, len(now))
        break


```

### 비고

- 다익스트라 알고리즘
