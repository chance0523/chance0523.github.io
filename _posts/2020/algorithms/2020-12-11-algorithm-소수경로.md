---
title: "[Python] BOJ 1963번. 소수경로"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-12-11 00:11:03 -0400
last_modified_at: 2020-12-11T00:11:03+08:00
---

# 1963번. 소수경로

### 문제 링크
- <https://www.acmicpc.net/problem/1963>{: target="\_blank"}

### 풀이 코드

```python
# 1963번. 소수경로


from collections import deque

# 일단 4자리 소수를 모두 담아준다
primeList = [False for i in range(10000)]
for i in range(2, 10000):
    if not primeList[i]:
        for j in range(i+i, 10000, i):
            primeList[j] = True


def bfs():
    q = deque([[before, 0]])
    visited = [False for i in range(10000)]
    # visited[before] = True

    while q:
        cur, time = q.popleft()
        if cur == after:  # 도착하면
            return time  # 리턴
        # 수 바꿔보기
        for i in range(4):
            for j in range(10):
                if i == 0 and j == 0:  # 첫번째 자리에 0이 오는 경우
                    continue
                nextNum = int(str(cur)[:i] + str(j) + str(cur)[i + 1 :])  # 다음 수
                # 소수이고, 방문하지 않았을 때
                if not primeList[nextNum] and not visited[nextNum]:
                    visited[nextNum] = True
                    q.append([nextNum, time+1]) # 다음 큐에 넣어줌


for _ in range(int(input())):
    before, after = map(int, input().split())
    if before == after:
        print(0)
        continue
    print(bfs())
```

### 비고