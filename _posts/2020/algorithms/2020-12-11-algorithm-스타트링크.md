---
title: "[Python] BOJ 5014번. 스타트링크"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ graph Gold5
meta_keywords: 알고리즘,백준,파이썬,5014번
date: 2020-12-11 12:08:19 -0400
last_modified_at: 2020-12-11T12:08:19+08:00
---

# 5014번. 스타트링크

### 문제 링크
- <https://www.acmicpc.net/problem/5014>{: target="\_blank"}

### 풀이 코드

```python
# 5014번. 스타트링크


from collections import deque
f, s, g, u, d = map(int, input().split())
# 총 f층, 스타트 링크 : g층
# 강호 현재 s층, 엘리베이터 타고 g층으로 이동하려고 함
# u,d 버튼만 있음

visited = [False for i in range(f+1)]

q = deque([[s, 0]])

ans = []

while q:
    cur = q[0][0]  # 현재 층
    time = q[0][1]  # 시간
    q.popleft()
    if cur == g:
        ans.append(time)
    if cur + u <= f and not visited[cur+u]:
        visited[cur + u] = True
        q.append([cur + u, time+1])
    if cur - d >= 1 and not visited[cur - d]:
        visited[cur - d] = True
        q.append([cur - d, time+1])

if ans:
    print(min(ans))
else:
    print('use the stairs')
```

### 비고