---
title: '[Python] BOJ 22858번. 원상 복구 (small)'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2021-08-26 19:00:25 -0400
last_modified_at: 2021-08-26T19:00:25+08:00
---

# 22858번. 원상 복구 (small)

### 문제 링크
- <https://www.acmicpc.net/problem/22858>{: target="\_blank"}

### 풀이 코드
- n이 10^4, k가 10^3이라 O(NK)에도 풀리는 문제입니다.
- 밥 먹으면서 봐서 문제가 잘 안 읽히긴 그냥 k번 돌면서 복구만 시켜주면 되는 문제인 것을 깨달았습니다.
- 처음 받는 D의 정보를 가공해줘야합니다. (dList_temp -> dList)
  - [D의 값, 인덱스]로 담아주고 정렬을 하면, **먼저 와야하는 S의 인덱스의 순서**대로 정렬되게 됩니다. 이해를 위해 문제의 예시에 대입하면
  - 문제의 D를 정렬하면 '[[1,2],[2,3],[3,1],[4,0],[5,4]]'와 같이 정렬이 되는데, 앞에서부터 각 요소의 1번째 인덱스를 보면, S[2]->S[3]->S[1]->S[0]->S[4] 순으로 P가 만들어지게 됩니다. (예제의 그림을 참고해보세요.)
- 위와 같이 가공된 정보를 통해 ans 리스트를 계속 갱신해주면 됩니다. O(NK)로 풀리는 문제여서 계속 temp 리스트를 만들어서 ans 리스트에 담아줘도 통과합니다.

```python
# 22858번. 원상 복구 (small)


n,k = map(int,input().split())
sList = list(map(int,input().split()))
dList_temp = list(map(int,input().split()))

# D의 정보 가공
dList = []
for i in range(n):
    dList.append([dList_temp[i],i])

dList.sort()

ans = [sList[i] for i in range(n)]
for i in range(k):
    temp = []
    for d in dList:
        temp.append(ans[d[1]])
    for j in range(n):
        ans[j] = temp[j]
print(*ans)
```

### 비고