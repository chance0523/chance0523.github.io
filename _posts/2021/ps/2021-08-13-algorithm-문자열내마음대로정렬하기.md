---
title: '[Python] Programmers. 문자열 내 마음대로 정렬하기'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,프로그래머스,파이썬,문자열 내 마음대로 정렬하기]
toc: true
toc_sticky: true
date: 2021-08-13 21:35:25 -0400
last_modified_at: 2021-08-13T21:35:25+08:00
---

# 소수찾기

### 문제 링크
- <https://programmers.co.kr/learn/courses/30/lessons/12925>{: target="\_blank"}

### 풀이 코드
- 'n번째 문자가 같은 단어가 여러개면 사전순으로 정렬한다.' -> 이것을 통해서 n번째 문자를 맨 앞으로 가져온 뒤 전체 리스트를 정렬하면 된다는 것을 알 수 있습니다.
- 문자열 바꾸기 (change) -> 정렬 -> 다시 바꿔주기 (rollback) 이러한 플로우로 구현하면 됩니다.

```python
# 문자열 내 마음대로 정렬하기
def change(s,n):
    temp = s[n] + s[:n] + s[n+1:]
    return temp

def rollback(s,n):
    temp = s[1:n+1] + s[0] + s[n+1:]
    return temp

def solution(strings, n):
    answer = []
    for i in range(len(strings)):
        strings[i] = change(strings[i], n)
    strings.sort()
    for i in range(len(strings)):
        answer.append(rollback(strings[i],n))
    return answer
```

### 비고