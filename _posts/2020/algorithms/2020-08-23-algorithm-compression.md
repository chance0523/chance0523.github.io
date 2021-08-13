---
title: "[Python] BOJ 1662번. 압축"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-08-23 03:10:29 -0400
last_modified_at: 2020-08-23T03:10:29+08:00
---

# 1662번. 압축

### 문제 링크
- <https://www.acmicpc.net/problem/1662>{: target="\_blank"}

### 풀이 코드

```python
# 1662번. 압축


s = input()
stack = []
b = [0 for i in range(len(s))]

for i in range(len(s)):  # 전처리
    if s[i] == '(':
        stack.append(i)
    elif s[i] == ')':
        b[stack.pop()] = i


def recur(left, right):
    result = 0
    while left < right:
        if s[left].isdigit():  # 괄호 안 숫자
            result += 1
            left += 1
        else:
            result -= 1  # K를 빼줌
            result += int(s[left-1]) * recur(left+1, b[left])
            left = b[left] + 1
    return result


print(recur(0, len(s)))
```

### 비고