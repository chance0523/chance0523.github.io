---
title: "[Python] BOJ 1316번. 그룹 단어 체커"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-09 20:14:12 -0400
last_modified_at: 2020-06-09T20:14:12+08:00
---

# 1316번. 그룹 단어 체커

### 문제 링크
- <https://www.acmicpc.net/problem/1316>{: target="\_blank"}

### 풀이 코드

```python
# 1316번. 그룹 단어 체커


n = int(input())
ans = 0


def iscon(s):
    alpha = [0]*26
    for i in range(len(s)):
        asc = ord(s[i])-97
        # 만약 글자가 나온적이 있고 앞 단어와는 다르면
        # 떨어져서 나온 것
        if alpha[asc] >= 1 and s[i] != s[i-1]:
            return False
        else:
            alpha[asc] += 1
    return True


for i in range(n):
    s = input()
    if iscon(s):
        ans += 1
print(ans)
```

### 비고