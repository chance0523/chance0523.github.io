---
title: "[Python] BOJ 1490번. 자리수로 나누기"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-10 01:17:54 -0400
last_modified_at: 2020-06-10T01:17:54+08:00
---

# 1490번. 자리수로 나누기

### 문제 링크
- <https://www.acmicpc.net/problem/1490>{: target="\_blank"}

### 풀이 코드

```python
# 1490번. 자리수로 나누기


# 0~9, 00~99, 000~999를 넣기 위함
iList = [str(i) for i in range(10000)]
for j in range(6):
    for i in range(len(iList)):
        if len(iList[i])+j <= 5:
            iList.append('0'*j+iList[i])
iList.sort()

n = input()
nList = list(map(int, n))
flag = True


# 뒤에 무언가를 넣어야할 때
def insertsomething():
    flag = True
    for i in range(1, 5):
        # 리스트에서 꺼내온다
        for k in iList:
            if len(k) == i:
                num = n+k
                for j in range(len(nList)):
                    if nList[j] != 0:
                        if int(num) % nList[j] == 0:
                            flag = True
                        else:
                            flag = False
                            break
                if flag:
                    print(int(num))
                    return


# n이 그 자체로 만족할 때
for j in range(len(nList)):
    if nList[j] != 0:
        if int(n) % nList[j] == 0:
            flag = True
        else:
            flag = False
            break
if flag:
    print(int(n))

# 뒤에 뭐를 넣어야할때
else:
    insertsomething()
```

### 비고