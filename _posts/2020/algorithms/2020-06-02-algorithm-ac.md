---
title: "[Python] BOJ 5430번. AC"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, Implement, Silver2]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,5430번
date: 2020-06-02 00:15:58 -0400
last_modified_at: 2020-06-02T00:15:58+08:00
---

# 5430번. AC

### 문제 링크
- <https://www.acmicpc.net/problem/5430>{: target="\_blank"}

### 풀이 코드

```python
# 5430번. AC


import sys
input = sys.stdin.readline

t = int(input())

for _ in range(t):
    p = list(input())
    n = int(input())

    # 배열의 길이가 0일때와 아닐때로 나눠야 int형 list로 바꿀 수 있음
    if n == 0:
        arr = input()
        arr = []
    else:
        arr = list(input().rstrip()[1:-1].split(','))
    # print(arr)

    reverseFlag = True
    errorFlag = True

    for pp in p:
        if pp == 'R':
            reverseFlag = not reverseFlag
        elif pp == 'D':
            if reverseFlag:  # 제대로된 순서
                if arr:
                    arr.pop(0)  # 맨 앞을 제거
                else:
                    errorFlag = False
                    break
            else:  # 거꾸로
                if arr:
                    arr.pop()  # 맨 뒤를 제거
                else:
                    errorFlag = False
                    break

    if errorFlag:
        if reverseFlag:  # 기존 순서
            print('['+','.join(arr)+']')
        else:
            print('['+','.join(reversed(arr))+']')

    else:
        print('error')
```

### 비고