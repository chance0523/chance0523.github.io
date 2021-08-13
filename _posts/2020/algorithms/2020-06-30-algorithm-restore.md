---
title: "[Python] BOJ 2312번. 수 복원하기"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-30 17:28:02 -0400
last_modified_at: 2020-06-30T17:28:02+08:00
---

# 2312번. 수 복원하기

### 문제 링크
- <https://www.acmicpc.net/problem/2312>{: target="\_blank"}

### 풀이 코드

```python
# 2312번. 수 복원하기


for _ in range(int(input())):
    n = int(input())
    num = 2
    # 딕셔너리에 인수:개수 형태로 넣어줌
    ansDict = {}
    for i in range(n+1):
        ansDict[i] = 0

    while True:
        # 다 나누어지면 종료
        if n == 1:
            break
        # 나누어떨어지지 않으면 다음 수로
        if n % num != 0:
            num += 1
        else:
            # 인수 check
            n /= num
            ansDict[num] += 1

    for i in ansDict.items():
        if i[1] != 0:
            print(i[0], i[1])
```

### 비고