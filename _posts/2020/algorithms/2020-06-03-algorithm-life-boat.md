---
title: "[Python] Programmers 구명보트"
excerpt: ''
comments: true

categories:
    - Algorithms
tags:
    - [Algorithms, Programmers, Python, Implement]
toc: true
toc_sticky: true
meta_keywords: 알고리즘,프로그래머스,파이썬
date: 2020-06-03 00:30:00 -0400
last_modified_at: 2020-06-03T00:30:00+08:00
---

# 영어 끝말잇기

### 문제 링크

- <https://programmers.co.kr/learn/courses/30/lessons/42885>{: target="\_blank"}

### 풀이 코드

```python
# 구명보트


def solution(people, limit):
    answer = 0
    people.sort()
    # i는 앞에서부터, j는 뒤에서부터
    i = 0
    j = len(people)-1
    while i <= j:
        answer += 1
        # 이 조합으로 태울 수 있으면 태우고 다음 조합
        if people[i]+people[j] <= limit:
            i += 1
            j -= 1
        # 태울 수 없으면 무거운 사람의 무게를 줄임
        else:
            j -= 1

    return answer
```

### 비고
