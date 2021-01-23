---
title: '[Python] BOJ 10816번. 숫자 카드 2'
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, BOJ, Python, 이분탐색, Silver4]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,백준,파이썬,10816번
date: 2020-05-14 12:13:03 -0400
last_modified_at: 2020-05-14T12:13:03+08:00
---

# 10816번. 숫자 카드 2

### 문제 링크

-   <https://www.acmicpc.net/problem/10816>{: target="\_blank"}

### 풀이 코드

```python
# 10816번. 숫자 카드

2_ = int(input())
nList = sorted(map(int, input().split()))
_ = int(input())
mList = list(map(int, input().split()))

i, m_dic = 0, {}

for m in sorted(mList):
    cnt = 0
    if m not in m_dic:
        while i < len(nList):
            # nList를 하나하나 지나면서
            # m과 같은지 확인
            if m == nList[i]:
                cnt += 1
                i += 1
            elif m > nList[i]:
                i += 1
            else:
                break
        m_dic[m] = cnt

print(' '.join(str(m_dic[m]) for m in mList))
```

### 비고
