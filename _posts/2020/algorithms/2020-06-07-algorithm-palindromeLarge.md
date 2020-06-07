---
title: "[Python] BOJ 14517번. 팰린드롬 개수 구하기 (Large)"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ DP Platinum5
meta_keywords: 알고리즘,백준,파이썬,14517번
date: 2020-06-07 22:43:27 -0400
last_modified_at: 2020-06-07T22:43:27+08:00
---

# 14517번. 팰린드롬 개수 구하기 (Large)

### 문제 링크
- <https://www.acmicpc.net/problem/14517>{: target="\_blank"}

### 풀이 코드

```python
# 14517번. 팰린드롬 개수 구하기 (Large)


import sys
input = sys.stdin.readline

# 참고 블로그 : https://www.crocus.co.kr/869

# dp[a][b] : a에서 b까지 인덱스의 단어중
# 팰린드롬이 되는 가짓수

s = input().rstrip()
dp = [[0 for i in range(1005)] for i in range(1005)]
mod = 10007

# 일단 기본적인 전처리
for i in range(len(s)):
    # 한 글자 (a)
    dp[i][i] = 1

    if i != len(s)-1:
        # aa -> a, a, aa
        if s[i] == s[i+1]:
            dp[i][i+1] = 3

        # ab -> a, b
        else:
            dp[i][i+1] = 2


for i in range(len(s)):
    for left in range(len(s)):
        right = left+i  # left <- i만큼의 길이 -> right

        if right >= len(s):
            break

        # 위의 블로그 참고
        dp[left][right] = dp[left+1][right] + \
            dp[left][right-1]-dp[left+1][right-1]

        # 음수가 되는 경우
        if dp[left][right] < 0:
            dp[left][right] += mod

        # 블로그 참고
        if s[left] == s[right]:
            dp[left][right] += dp[left+1][right-1]+1

        dp[left][right] %= mod

print(dp[0][len(s)-1] % 10007)
```

### 비고