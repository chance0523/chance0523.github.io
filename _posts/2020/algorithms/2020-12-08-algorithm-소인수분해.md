---
title: "[Python] BOJ 11653번. 소인수분해"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ math Silver4
meta_keywords: 알고리즘,백준,파이썬,11653번
date: 2020-12-08 01:48:48 -0400
last_modified_at: 2020-12-08T01:48:48+08:00
---

# 11653번. 소인수분해

### 문제 링크
- <https://www.acmicpc.net/problem/11653>{: target="\_blank"}

### 풀이 코드

```python
# 11653번. 소인수분해


n = int(input())
ans = []

num = 2  # 2부터 시작
while n != 1:  # n이 1이면 종료
    if n % num == 0:  # 인수라면 리스트에 넣어주기
        ans.append(num)
        n //= num  # 나눠주기
    else:  # 인수가 아니라면 다음 수로
        num += 1

for a in ans:
    print(a)
```

### 비고