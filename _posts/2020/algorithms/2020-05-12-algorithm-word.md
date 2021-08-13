---
title: '[Python] BOJ 1157번. 단어 공부'
excerpt: ''
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-05-12 21:20:00 -0400
last_modified_at: 2020-05-12T21:20:00+08:00
---

# 1157번. 단어 공부

### 문제 링크

-   <https://www.acmicpc.net/problem/1157>{: target="\_blank"}

### 풀이 코드

```python
# 1157번. 단어 공부

s = input()
s = s.lower() # 모두 소문자로 변환
ss = list(set(s)) # 중복을 제거
ssList = [] # 문자의 갯수를 담는 리스트
for c in ss:
    ssList.append(s.count(c))

M = max(ssList)
if ssList.count(M) >= 2:
    print('?')
else:
    idx = ssList.index(M)
    print(ss[idx].upper())
```

### 비고
