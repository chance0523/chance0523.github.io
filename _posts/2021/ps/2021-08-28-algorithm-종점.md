---
title: '[Python] BOJ 22867번. 종점'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-08-28 11:00:25 -0400
last_modified_at: 2021-08-28T11:00:25+08:00
---

# 22867번. 종점

### 문제 링크
- <https://www.acmicpc.net/problem/22867>{: target="\_blank"}

### 풀이 코드
- 놀랍게도 문자열 파싱을 하지 않아도 되는 문제였습니다. 어차피 문자열대로 정렬해도 순서가 잘 맞기 때문이죠. 저는 무식하게 파싱을 했으니 '만약에 파싱을 하면 이렇게 풀면 된다~'정도로 봐주시면 되겠습니다.
- 지문이 살짝 헷갈리는데, 결국 **'버스 동접자 수'**의 최대를 구하시면 됩니다.
- time이라는 리스트에 ['시각', '출입구분']로 넣어주시면 되는데, 문제에서 `만약 같은 시각에 종점에 들어오는 버스 A와 종점에서 출발하는 버스 B가 있을 경우는 버스 B가 먼저 종점에서 출발하고 그 다음으로 버스 A가 종점으로 들어온다.`와 같은 조건이 있습니다. '동시간대에 마주치는 버스가 있으면 종점에 있는 버스가 먼저 출발해서 자리를 만들어둔다'정도로 생각하고 리스트의 '출입구분'에 넣어줄 값을 정하시면 됩니다.
- '출입구분'에 들어오는 버스는 2, 나가는 버스는 1로 정하고 '정렬'을 해주면 우리가 원하는 순서로 정렬이 되게 됩니다.
- 이제 time 리스트를 돌면서 버스가 들어오면 cnt(정비공간)를 늘려주고, 나가면 cnt를 감소시켜주면 됩니다. 버스가 종점에서 나갈때 ans를 갱신해주면 '종점의 버스 동접자 수'의 최대를 구할 수 있게 됩니다.

```python
# 22867번. 종점


import sys
input =  sys.stdin.readline


def convert(t): # 파싱하지 않아도 됩니다...
    h = int(t[:2])
    m = int(t[3:5])
    s = int(t[6:8])
    ss = int(t[9:])
    t = ss + s*1000 + m*1000*60 + h*1000*60*60
    return t

n = int(input())
nList = []
time = []
for i in range(n):
    _in,out = input().rstrip().split()
    time.append([convert(_in), 2]) # 종점에서는 출발이 먼저
    time.append([convert(out), 1])

time.sort()

ans = 0
cnt = 0
for i in range(len(time)):
    if time[i][1] == 2: # 종점으로 들어옴 (자리 필요)
        cnt += 1
    else: # 종점에서 나감
        ans = max(ans,cnt)
        cnt -= 1
print(ans)

```

### 비고