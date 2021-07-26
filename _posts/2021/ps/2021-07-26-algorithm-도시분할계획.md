---
title: '[Python] BOJ 1647번. 소수의 연속합'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬,1647번]
toc: true
toc_sticky: true
date: 2021-07-26 11:20:25 -0400
last_modified_at: 2021-07-26T11:20:25+08:00
---

# 1647번. 도시 분할 계획

### 문제 링크
- <https://www.acmicpc.net/problem/1647>{: target="\_blank"}

### 풀이 코드
- 전형적인 MST 문제에서 살짝, 아주 살짝 변형 되었습니다.
- '마을의 이장은 마을을 두 개의 분리된 마을로 분할할 계획을 가지고 있다.' <- 이 문장이 핵심입니다.
- 기존의 MST에서는 모든 집들이 연결 되어있지만, 해당 문제에서는 최소 한 집 정도는 따로 있어도 됩니다.
- **-> MST를 쓰고 제일 비싼 비용의 선을 지우면 두개로 분리되면서 최소값이 나온다!**
- 풀이에서는 sort를 통해 비용이 작은 선부터 넣으면서 마지막 한 선은 넣지 않고 break 처리하여 구현하였습니다.

```python
# 1647번. 도시 분할 계획

# 마을의 이장은 마을을 두 개의 분리된 마을로 분할할 계획을 가지고 있다.
# -> MST를 쓰고 제일 비싼 비용의 선을 지우면 두개로 분리되면서 최소값이 나온다!
import sys

input = sys.stdin.readline


def make(parent):
    for i in range(v + 1):
        parent[i] = i
    return parent


def find(parent, a):
    if parent[a] == a:
        return a
    parent[a] = find(parent, parent[a])
    return parent[a]


def union(parent, a, b):
    a = find(parent, a)
    b = find(parent, b)
    if a > b:
        parent[a] = b
        return True
    elif a < b:
        parent[b] = a
        return True
    return False


n, m = map(int, input().rstrip().split())
parent = [i for i in range(n + 1)]  # make
edges = []
cnt, ans = 0, 0
for _ in range(m):
    a, b, c = map(int, input().rstrip().split())
    edges.append([c, a, b])
edges.sort()

for edge in edges:
    if union(parent, edge[1], edge[2]):
        ans += edge[0]
        cnt += 1
        if cnt == n - 2:
            break

print(ans)
```

### 비고