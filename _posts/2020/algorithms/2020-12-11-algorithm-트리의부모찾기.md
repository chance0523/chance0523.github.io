---
title: "[Python] BOJ 11725번. 트리의 부모 찾기"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-12-11 11:20:09 -0400
last_modified_at: 2020-12-11T11:20:09+08:00
---

# 11725번. 트리의 부모 찾기

### 문제 링크
- <https://www.acmicpc.net/problem/11725>{: target="\_blank"}

### 풀이 코드

```python
# 11725번. 트리의 부모 찾기


from collections import deque

n = int(input())
nList = [[] for i in range(n+1)]
for i in range(n-1):
    a, b = map(int, input().split())
    nList[a].append(b)
    nList[b].append(a)

q = deque([1])
visited = [False for i in range(n+1)]
ans = {}
for i in range(1, n + 1):
    ans[i] = []

while q:
    parent = q.popleft()
    for child in nList[parent]:  # 이 노드의 자식들
        if not visited[child]:
            ans[child] = parent  # 부모를 저장해줌
            q.append(child)
            visited[child] = True

for i in range(2, n + 1):
    print(ans[i])
```

### 비고