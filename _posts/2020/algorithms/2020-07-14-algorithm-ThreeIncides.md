---
title: "[Python] codeforces edu 91 A. Three Incides"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-07-14 22:05:00 -0400
last_modified_at: 2020-07-14T22:05:00+08:00
---

# A. Three Incides

### 문제 링크

- <https://codeforces.com/problemset/problem/1380/A>{: target="\_blank"}

### 풀이 코드

```python
# A. Three Incides

import sys
input = sys.stdin.readline

t = int(input())


def func():
    for i in range(1, n-1):
        # permutation이기 때문에 (1~n이 하나씩 나오기 때문에)
        # 순서대로 정렬이 아니라면 한 쪽에서 분명 값이 역전되므로
        # 연속한 답이 무조건 있다.
        # 1 2 3 4 에서 5를 아무데나 넣어도 연속한 답이 나온다.
        if nList[i] > nList[i-1] and nList[i] > nList[i+1]:
            print("YES")
            print(i, i+1, i+2)
            return
    return print('NO')


for _ in range(t):
    n = int(input())
    nList = list(map(int, input().split()))

    func()
```

### 비고
