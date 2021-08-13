---
title: '[Python] Programmers. 2020 카카오 인턴십 - 키패드 누르기'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,프로그래머스,파이썬,카카오인턴십]
toc: true
toc_sticky: true
date: 2021-08-13 21:55:25 -0400
last_modified_at: 2021-08-13T21:55:25+08:00
---

# 2020 카카오 인턴십 - 키패드 누르기

### 문제 링크
- <https://programmers.co.kr/learn/courses/30/lessons/67256>{: target="\_blank"}

### 풀이 코드
- 역시 카카오. 구현 연습 하기 좋은 문제입니다.
- 왼손만, 또는 오른손만 움직이는 경우의 구현은 다들 쉽게 구현하실겁니다.
- 문제가 되는 가운데 있는 번호의 경우도 조건을 차근차근 풀어가면 풀 수 있습니다.
  - 왼손이 올려져있는 위치에서 타겟넘버까지의 거리를 구합니다. (간단한 좌표화를 시켜주면 됩니다.)
  - 오른손이 올려져있는 위치에서 타겟넘버까지의 거리를 구합니다.
  - 거리를 구해줍니다.
  - 비교 한 뒤 같으면 OO손잡이를 보고, 다르면 조건대로 움직이면 됩니다.
  
```python
# 2020 카카오 인턴십 - 키패드 누르기
def getDistance(num, cur):
    nx = getX(num)
    ny = getY(num)
    cx = getX(cur)
    cy = getY(cur)
    dist = abs(nx-cx) + abs(ny-cy)
    return dist


def getX(k):
    if k in [1,4,7,-1]:
        return 0
    elif k in [2,5,8,0]:
        return 1
    else:
        return 2
    
    
def getY(k):
    if k in [1,2,3]:
        return 0
    elif k in [4,5,6]:
        return 1
    elif k in [7,8,9]:
        return 2
    else:
        return 3
    

def solution(numbers, hand):
    answer = ''
    # 맨처음에는 *, # 에서 각각 시작한다
    # (*, #) 은 다시 방문하지 않는다.
    '''
    1 2 3
    4 5 6
    7 8 9
    * 0 #
    '''
    cur_l = -1
    cur_r = -1
    for i in range(len(numbers)):
        num = numbers[i]
        if num in [1,4,7]: # 왼손
            answer+='L'
            cur_l = num
        elif num in [3,6,9]: # 오른손
            answer+='R'
            cur_r = num
        else: # 2,5,8,0
            lD = getDistance(num, cur_l)
            rD = getDistance(num, cur_r)
            if lD == rD:
                if hand == 'left':
                    answer+='L'
                    cur_l = num
                else:
                    answer+='R'
                    cur_r = num
            elif lD < rD:
                answer+='L'
                cur_l = num
            else:
                answer+='R'
                cur_r = num
    return answer
```

### 비고