---
title: '[Python] BOJ 1152번. 단어의 개수'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-09-22 11:30:25 -0400
last_modified_at: 2021-09-22T11:30:25+08:00
---

# 1152번. 단어의 개수

### 문제 링크
- <https://www.acmicpc.net/problem/1152>{: target="\_blank"}

### 풀이 코드
- 파이썬의 `split()`을 연습 할 수 있는 문제입니다.

```python
# input
The Curious Case of Benjamin Button

# input().split()을 한 뒤
['The', 'Curious', 'Case', 'of', 'Benjamin', 'Button']

# len()을 통해 답 출력
```


```python
# 1152번. 단어의 개수
print(len(input().split()))
```

### 비고