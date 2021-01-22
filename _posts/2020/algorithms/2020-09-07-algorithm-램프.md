---
title: "[Python] BOJ 1034번. 램프"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ bruteforce Gold5
meta_keywords: 알고리즘,백준,파이썬,1034번
date: 2020-09-07 23:11:19 -0400
last_modified_at: 2020-09-07T23:11:19+08:00
---

# 1034번. 램프

### 문제 링크
- <https://www.acmicpc.net/problem/1034>{: target="\_blank"}

### 풀이 코드

```python
# 1034번. 램프


n, m = map(int, input().split())
box = [input() for i in range(n)]
k = int(input())

# https://blog.encrypted.gg/290

'''
초기상태가 다른 행 i,j는 절대 동시에 켜져있는 행이 될 수 없다.
k번 눌러 켜져있게 만들 수 있는 행들에 대해서 초기 상태가 
가장 많이 동일한 것들의 개수를 반환
'''


'''
그 행에 있는 0의 개수가 k를 2로 나눈 나머지와 동일한가
그 행에 있는 0의 개수가 k이하인가
'''

cnt = [0 for i in range(n)]
if k % 2 != 0:
    for i in range(n):
        zero = box[i].count('0')
        if zero % 2 and zero <= k:
            for j in range(n):
                if box[i] == box[j]:
                    cnt[i] += 1
else:
    for i in range(n):
        zero = box[i].count('0')
        if not zero % 2 and zero <= k:
            for j in range(n):
                if box[i] == box[j]:
                    cnt[i] += 1

print(max(cnt))
```

### 비고