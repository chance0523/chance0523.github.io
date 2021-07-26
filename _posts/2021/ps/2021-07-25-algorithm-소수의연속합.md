---
title: '[Python] BOJ 1644번. 소수의 연속합'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬,1644번]
toc: true
toc_sticky: true
date: 2021-07-25 11:20:25 -0400
last_modified_at: 2021-07-25T11:20:25+08:00
---

# 1644번. 소수의 연속합

### 문제 링크
- <https://www.acmicpc.net/problem/1644>{: target="\_blank"}

### 풀이 코드

- 에라토스테네스의 체와 두포인터를 사용하는 문제입니다.
- 먼저 체를 통해서 소수들만 골라줍니다.
- 두포인터를 사용하여 현재 합이 n보다 작으면 오른쪽으로 늘려주고, 크면 왼쪽을 빼줍니다.
- 같을 경우는 오른쪽을 늘려줍니다.
- 아래 코드에서는 pList의 범위를 `n+1`로 잡았지만, 마음 편하게 `4000000+1`로 잡고 아래 `int(math.sqrt(n) + 1`도 `3000`정도로 잡는 것이 편합니다. (실제로 제출은 이렇게 했습니다!)

```python
# 1644번. 소수의 연속합


import math, sys

n = int(input())
if n == 1:
    print(0)
    sys.exit()
# 소수 리스트 만들어주기 (에라토스테네스의 체)
pList = [True for i in range(n + 1)]
pList[1] = False
for i in range(2, int(math.sqrt(n) + 1)):
    if pList[i]:
        for j in range(i + i, n + 1, i):
            pList[j] = False

onlyPrimes = []
for i in range(2, n + 1):
    if pList[i]:
        onlyPrimes.append(i)

ans = 0
l = 0
r = 0
cur = onlyPrimes[0]
while True:
    if l > r:
        break
    if cur > n:
        cur -= onlyPrimes[l]
        l += 1
    elif cur < n:
        r += 1
        if r == len(onlyPrimes):
            break
        cur += onlyPrimes[r]
    else:
        ans += 1
        r += 1
        if r == len(onlyPrimes):
            break
        cur += onlyPrimes[r]
print(ans)
```

### 비고