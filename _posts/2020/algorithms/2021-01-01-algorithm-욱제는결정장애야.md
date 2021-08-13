---
title: "[Python] BOJ 14646번. 욱제는 결정장애야!!"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-01-01 23:32:40 -0400
last_modified_at: 2021-01-01T23:32:40+08:00
---

# 14646번. 욱제는 결정장애야!!

### 문제 링크
- <https://www.acmicpc.net/problem/14646>{: target="\_blank"}

### 풀이 코드

```python
# 14646번. 욱제는 결정장애야!!


n = int(input())
nList = list(map(int, input().split()))
ans = 0
cnt = 0
menu = [False] * 111111

for num in nList:
    if not menu[num]:  # 한번도 안 나왔다면
        cnt += 1
        menu[num] = True
    else:
        cnt -= 1
        menu[num] = False

    ans = max(ans, cnt)  # 붙어있는 스티커 최대 개수 업데이트

print(ans)
```

### 비고