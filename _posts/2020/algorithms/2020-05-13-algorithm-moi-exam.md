---
title: '[Python] Programmers. 모의고사'
excerpt: ''
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,프로그래머스,파이썬]
toc: true
toc_sticky: true
date: 2020-05-13 18:50:00 -0400
last_modified_at: 2020-05-13T18:50:00+08:00
---

# 완전탐색 | 모의고사

### 문제 링크

-   <https://programmers.co.kr/learn/courses/30/lessons/42840>{: target="\_blank"}

### 풀이 코드

```python
# 모의고사


def solution(answers):
    l=len(answers)
    s1 = [1,2,3,4,5]
    s2=[2,1,2,3,2,4,2,5] # 8
    s3=[3,3,1,1,2,2,4,4,5,5] # 10

    c1=c2=c3=0

    for i in range(len(answers)):
        if answers[i]==s1[i%5]:
            c1+=1
        if answers[i]==s2[i%8]:
            c2+=1
        if answers[i]==s3[i%10]:
            c3+=1

    c=[c1,c2,c3]
    M=max(c1,c2,c3)
    answer = []
    for i in range(3):
        if c[i]==M:
            answer.append(i+1)
    return answer
```

### 비고
