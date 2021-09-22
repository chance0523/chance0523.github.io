---
title: '[Python] BOJ 1302번. 베스트셀러'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-09-22 11:20:25 -0400
last_modified_at: 2021-09-22T11:20:25+08:00
---

# 1302번. 베스트셀러

### 문제 링크
- <https://www.acmicpc.net/problem/1302>{: target="\_blank"}

### 풀이 코드
- 파이썬의 딕셔너리 자료구조를 연습해 볼 수 있는 문제입니다.
- 책들을 딕셔너리에 {책 이름: 팔린 권 수} 형식으로 넣어줍니다.
- dict.keys()를 이용하여 받은 책들을 탐색하며 베스트셀러를 찾아줍니다.
- `가장 많이 팔린 책이 여러 개일 경우에는 사전 순으로 가장 앞서는 제목을 출력한다.`라는 조건이 있으므로 현재까지의 베스트셀러와 동률인 책이 나왔을 때 비교를 해줍니다.
- n이 작아서 리스트로 저장한 뒤 정렬을 해주는 방식으로 풀어도 될듯합니다.

```python
# 1302번. 베스트셀러


n = int(input())
bDict = {}
for i in range(n):
    s = input().rstrip()
    # 처음 받은 입력인지 확인
    if s not in bDict:
        bDict[s] = 1
    else:
        bDict[s] += 1

ans = 0
ansBook = ''
for k in bDict.keys():
    if ans < bDict[k]:
        ans = bDict[k]
        ansBook = k
    elif ans == bDict[k]:
        if ansBook > k:
            ansBook = k

print(ansBook)

```

### 비고