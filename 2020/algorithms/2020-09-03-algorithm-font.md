---
title: "[Python] BOJ 9997번. 폰트"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ bruteforce Gold2
meta_keywords: 알고리즘,백준,파이썬,9997번
date: 2020-09-03 09:34:35 -0400
last_modified_at: 2020-09-03T09:34:35+08:00
---

# 9997번. 폰트

### 문제 링크
- <https://www.acmicpc.net/problem/9997>{: target="\_blank"}

### 풀이 코드

```python
# 9997번. 폰트


n = int(input())
nList = [0 for i in range(n)]

mm = (1 << 26)-1
ans = 0
for i in range(n):
    s = list(input())
    for j in range(len(s)):
        s[j] = ord(s[j])-ord('a')
        temp = 1 << s[j]
        nList[i] |= temp


def func(cnt, cur):
    global ans
    if cnt == n:
        if mm == cur:
            ans += 1
        return

    func(cnt+1, cur | nList[cnt])
    func(cnt+1, cur)


func(0, 0)

print(ans)
```

### 비고