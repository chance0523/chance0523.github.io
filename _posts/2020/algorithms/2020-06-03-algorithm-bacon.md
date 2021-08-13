---
title: "[Python] BOJ 1389번. 케빈 베이컨의 6단계 법칙"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Graph, Silver1]
toc: true
toc_sticky: true
date: 2020-06-03 02:08:45 -0400
last_modified_at: 2020-06-03T02:08:45+08:00
---

# 1389번. 케빈 베이컨의 6단계 법칙

### 문제 링크
- <https://www.acmicpc.net/problem/1389>{: target="\_blank"}

### 풀이 코드

```python
# 1389번. 케빈 베이컨의 6단계 법칙


import sys
input = sys.stdin.readline

n, m = map(int, input().split())
re = [[0]*(n+1) for _ in range(n+1)]

for i in range(m):
    a, b = map(int, input().split())
    re[a][b] = 1
    re[b][a] = 1

for p in range(1, n+1):
    for i in range(1, n+1):
        for j in range(1, n+1):
            if i == j:
                continue
            else:
                if re[i][p] and re[p][j]:
                    if re[i][j] == 0:
                        re[i][j] = re[i][p]+re[p][j]
                    else:
                        re[i][j] = min(re[i][j], re[i][p]+re[p][j])

ans = []
for i in re:
    ans.append(sum(i))

# 가장 작은 값을 찾는다
minn = min(ans[1:])
# 여러 개라면 index()를 통해서 제일 앞에 있는 인덱스를 반환
print(ans.index(minn))
```

### 비고