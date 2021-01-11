---
title: "[Python] BOJ 15947번. 아기 석환 뚜루루 뚜루"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ case_work Bronze
meta_keywords: 알고리즘,백준,파이썬,15947번
date: 2021-01-10 16:51:08 -0400
last_modified_at: 2021-01-10T16:51:08+08:00
---

# 15947번. 아기 석환 뚜루루 뚜루

### 문제 링크
- <https://www.acmicpc.net/problem/15947>{: target="\_blank"}

### 풀이 코드

```python
# 15947번. 아기 석환 뚜루루 뚜루


mList = ['baby', 'sukhwan', 'tururu', 'turu',
         'very', 'cute', 'tururu', 'turu',
         'in', 'bed', 'tururu', 'turu',
         'baby', 'sukhwan']  # 14개 단어

n = int(input())-1
ans = ''
num = n % 14
numList = [2, 3, 6, 7, 10, 11]
if num in numList:
    k = n // 14
    if k >= 3:  # ru가 5번이상 반복 (기본 한번)
        if mList[num] == 'tururu':
            ans = f'tu+ru*{k+2}'
        else:
            if k == 3:
                ans = mList[num] + 'ru' * k
            else:
                ans = f'tu+ru*{k+1}'
    else:
        ans = mList[num] + 'ru' * k
else:
    ans = mList[num]
print(ans)
```

### 비고