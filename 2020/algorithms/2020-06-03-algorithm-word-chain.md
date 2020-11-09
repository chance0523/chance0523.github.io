---
title: "[Python] Programmers 영어 끝말잇기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm Programmers string
meta_keywords: 알고리즘,프로그래머스,파이썬
date: 2020-06-03 00:28:00 -0400
last_modified_at: 2020-06-03T00:28:00+08:00
---

# 영어 끝말잇기

### 문제 링크

- <https://programmers.co.kr/learn/courses/30/lessons/12981>{: target="\_blank"}

### 풀이 코드

```python
# 영어 끝말잇기


def solution(n, words):
    answer = []
    wordDict = {}
    cnt = 0
    ll = len(words)
    for i in range(ll):
        if i >= 1 and words[i][0] != words[i-1][-1]:  # 끝말잇기가 안될때
            answer.append([(i % n)+1, (i//n)+1])
            return answer[0]
        else:  # 끝말잇기가 될 때
            if words[i] not in wordDict:
                wordDict[words[i]] = [(i % n)+1, (i//n)+1]
            elif words[i] in wordDict:  # 이미 말 한 단어 (딱 걸렸다!)
                answer.append([(i % n)+1, (i//n)+1])
                return answer[0]
    # 아무 이상 없을 때
    answer.append([0, 0])
    return answer[0]
```

### 비고
