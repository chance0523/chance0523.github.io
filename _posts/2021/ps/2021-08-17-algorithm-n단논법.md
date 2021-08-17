---
title: '[Python] BOJ 15723번. n단 논법'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-08-17 10:45:25 -0400
last_modified_at: 2021-08-17T10:45:25+08:00
---

# 15723번. n단 논법

### 문제 링크
- <https://www.acmicpc.net/problem/15723>{: target="\_blank"}

### 풀이 코드
- 플로이드-와샬 알고리즘을 생각하는 것이 이 문제의 핵심입니다.
- 먼저 입력된 알파벳들을 숫자로 매핑해주고 리스트에 담습니다.
- 그 뒤에는 플로이드-와샬 알고리즘을 통해 값들을 갱신해줍니다.
- 모든 루프를 돈 뒤에도 값이 한 번도 갱신되지 못했다면 갈 수 없는 경로 (F)입니다.

```python
# 15723번. n단 논법


n = int(input())
dist = [[1e9 for i in range(26)] for i in range(26)] # 총 26가지의 알파벳
for i in range(n):
    inList = input().split()
    start = ord(inList[0]) - ord('a') # 숫자 형태로 변환해줍니다.
    end = ord(inList[2]) - ord('a')
    dist[start][end] = 1 # 1로 변경

# 플로이드-와샬
for k in range(26):
    for i in range(26):
        for j in range(26):
            dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j])

m = int(input())
for i in range(m):
    inList = input().split()
    start = ord(inList[0]) - ord('a')
    end = ord(inList[2]) - ord('a')
    if dist[start][end] < 1e9: # 갈 수 있는 거리라면
        print('T')
    else:
        print('F')
```

### 비고