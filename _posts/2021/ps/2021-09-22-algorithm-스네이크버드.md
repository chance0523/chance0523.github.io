---
title: '[Python] BOJ 16435번. 스네이크버드'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-09-22 11:10:25 -0400
last_modified_at: 2021-09-22T11:10:25+08:00
---

# 16435번. 스네이크버드

### 문제 링크
- <https://www.acmicpc.net/problem/16435>{: target="\_blank"}

### 풀이 코드
- 간단한 정렬 문제입니다. 파이썬의 `sort()`를 사용하면 쉽게 풀 수 있습니다.
- 받은 입력을 정렬을 합니다.
- 앞에서부터 먹어가면서 몸 길이를 늘려줍니다.
- 먹을 수 없는 과일이 나오면 break하고 길이를 출력합니다.

```python
# 16435번. 스네이크버드


# 입력
n, l = map(int, input().split())
hList = list(map(int, input().split()))

# 정렬
hList.sort()

for i in range(n):
    if hList[i] > l:
        break
    l += 1

# 출력
print(l)
```

### 비고