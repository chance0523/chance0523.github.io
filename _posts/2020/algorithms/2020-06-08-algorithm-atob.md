---
title: "[Python] BOJ 16953번. A->B"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-08 16:44:33 -0400
last_modified_at: 2020-06-08T16:44:33+08:00
---

# 16953번. A->B

### 문제 링크
- <https://www.acmicpc.net/problem/16953>{: target="\_blank"}

### 풀이 코드

```python
# 16953번. A->B


a, b = map(int, input().split())

# b->a로 생각
# b가 짝수거나 마지막 자리수가 1인 수밖에 없다

cnt = 0
while True:
    if a > b:
        print(-1)
        break
    if a == b:
        print(cnt+1)
        break

    # b가 짝수
    if b % 2 == 0:
        b /= 2
    # 마지막 자리수가 1
    elif b % 10 == 1:
        b = b//10
    else:
        print(-1)
        break

    cnt += 1
```

### 비고