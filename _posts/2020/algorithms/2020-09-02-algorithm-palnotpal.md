---
title: "[Python] BOJ 15927번. 회문은 회문아니야!!"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-09-02 00:28:36 -0400
last_modified_at: 2020-09-02T00:28:36+08:00
---

# 15927번. 회문은 회문아니야!!

### 문제 링크
- <https://www.acmicpc.net/problem/15927>{: target="\_blank"}

### 풀이 코드

```python
# 15927번. 회문은 회문아니야!!


s = input()

isnotPalindrome = False
isnotSame = False
# 전체가 같은 문자면 -1
# 전체가 palindrome이 아니면 len(s)
# 전체가 palindrome이면 len(s)-1

if s == s[0]*len(s):  # 전체가 같은 문자열
    print(-1)

elif s != s[::-1]:  # s[::-1]은 문자열 뒤집은것. 비교해서 다르면 팰린드롬이 아니다
    print(len(s))

else:  # 그 외의 경우
    print(len(s)-1)
```

### 비고