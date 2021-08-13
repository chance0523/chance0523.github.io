---
title: "[Python] BOJ 2563번. 색종이"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-09-18 22:57:27 -0400
last_modified_at: 2020-09-18T22:57:27+08:00
---

# 2563번. 색종이

### 문제 링크
- <https://www.acmicpc.net/problem/2563>{: target="\_blank"}

### 풀이 코드

```python
# 2563번. 색종이


fullmap = [[0 for i in range(101)] for i in range(101)]

for t in range(int(input())):
    c, r = map(int, input().split())
    # 크기는 10x10
    for i in range(r, r+10):
        for j in range(c, c+10):
            # 색종이가 도화지 밖으로 나가는 경우는 없다.
            fullmap[i][j] += 1

# 모든 색종이를 덮은 뒤 덮인 넓이 확인
ans = 0
for i in range(101):
    for j in range(101):
        if fullmap[i][j] >= 1:
            ans += 1
print(ans)
```

### 비고