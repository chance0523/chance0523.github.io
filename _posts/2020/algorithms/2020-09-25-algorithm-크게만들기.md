---
title: "[Python] BOJ 2812번. 크게 만들기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ greedy Gold5
meta_keywords: 알고리즘,백준,파이썬,2812번
date: 2020-09-25 12:47:46 -0400
last_modified_at: 2020-09-25T12:47:46+08:00
---

# 2812번. 크게 만들기

### 문제 링크
- <https://www.acmicpc.net/problem/2812>{: target="\_blank"}

### 풀이 코드

```python
# 2812번. 크게 만들기


n, k = map(int, input().split())
initk = n-k
s = list(input())
ans = []

for i in range(len(s)):
    if k == 0:  # 모두 다 지웠으면 그 다음은 그냥 계속 넣어줌.
        ans.append(s[i])
        continue
    if not ans:  # 스택이 비어있으면 무조건 넣어준다
        ans.append(s[i])
    else:
        if ans[-1] >= s[i]:  # 더 작은수는 일단 넣어줌
            ans.append(s[i])
        else:  # 큰 수가 나오면 계속 pop하고 k--
            while ans and ans[-1] < s[i] and k > 0:
                ans.pop()
                k -= 1
            ans.append(s[i])

print(''.join(ans[:initk]))
```

### 비고