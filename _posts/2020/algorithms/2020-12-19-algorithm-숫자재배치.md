---
title: "[Python] BOJ 16943번. 숫자 재배치"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ bruteforce Silver1
meta_keywords: 알고리즘,백준,파이썬,16943번
date: 2020-12-19 17:09:46 -0400
last_modified_at: 2020-12-19T17:09:46+08:00
---

# 16943번. 숫자 재배치

### 문제 링크
- <https://www.acmicpc.net/problem/16943>{: target="\_blank"}

### 풀이 코드

```python
# 16943번. 숫자 재배치


from itertools import permutations


def makeNum(nList):
    num = ''.join(nList)
    if len(str(int(num))) == len(nList):  # 0으로 시작하지 않는 경우만
        return int(num)


a, b = map(int, input().split())
a = list(str(a))  # 한 자리씩 띄어준다
pList = list(permutations(a, len(a)))  # 모든 순열 생성
ans = 0
min_diff = 1e9
for i in range(len(pList)):
    num = makeNum(pList[i])
    if num and b > num and b - num < min_diff:  # 차이가 가장 작으면
        ans = num
        min_diff = abs(b - num)

if min_diff == 1e9:  # 만들 수 없었으면
    print(-1)
else:
    print(ans)
```

### 비고