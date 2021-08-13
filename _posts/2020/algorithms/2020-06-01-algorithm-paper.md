---
title: "[Python] BOJ 1780번. 종이의 개수"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-01 23:21:39 -0400
last_modified_at: 2020-06-01T23:21:39+08:00
---

# 1780번. 종이의 개수

### 문제 링크
- <https://www.acmicpc.net/problem/1780>{: target="\_blank"}

### 풀이 코드

```python
# 1780번. 종이의 개수


import sys
input = sys.stdin.readline

# 분할 정복 너무 어렵다...
n = int(input())
box = [[0 for i in range(n)] for i in range(n)]
for i in range(n):
    box[i] = list(map(int, input().split()))
ans = [0, 0, 0]  # -1,0,1

# 같은 숫자로 된 종이인지 파악


def same(x, y, n):
    for i in range(x, x+n):
        for j in range(y, y+n):
            if box[x][y] != box[i][j]:
                return False
    return True


def paper(x, y, n):
    # 이 종이가 같은 숫자로 되어있을때
    if same(x, y, n):
        ans[box[x][y]+1] += 1
        return

    else:
        # 그렇지 않으면 9분할 (가로 세로 1/3)
        m = n//3
        for i in range(3):
            for j in range(3):
                # 9개로 나뉜 종이들에 대해 재귀
                paper(x+i*m, y+j*m, m)


# 시작
paper(0, 0, n)

for a in ans:
    print(a)
```

### 비고