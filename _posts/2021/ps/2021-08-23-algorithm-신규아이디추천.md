---
title: '[Python] Programmers. 2021 카카오 블라인드 - 신규 아이디 추천'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,프로그래머스,파이썬,카카오블라인드]
toc: true
toc_sticky: true
date: 2021-08-23 21:55:25 -0400
last_modified_at: 2021-08-23T21:55:25+08:00
---

# 2021 카카오 블라인드 채용 - 신규 아이디 추천

### 문제 링크
- <https://programmers.co.kr/learn/courses/30/lessons/72410>{: target="\_blank"}

### 풀이 코드
- 주어진 1~7단계를 잘 구현만 하면 되는 문제입니다. 브론즈~실버 수준의 구현 7개를 합쳐놓은 느낌입니다.
- 1단계
  - 파이썬의 `lower()`함수를 사용하면 됩니다.
- 2단계
  - 파이썬의 `isalpha()`, `isnumeric()` 함수를 사용해도 되지만, 기억이 안 난다면 아스키코드를 이용해서 풀면 됩니다. 정확한 아스키코드 number대신에 `ord()`로 그때그때 변환해서 비교해주면 됩니다.
- 3단계
  - 제일 까다로울 수도 있는 단계입니다.
  - 마침표(.)이 나왔는지 가지고 있다가 (flag로 풀어도 될듯합니다) 마침표가 아닌 문자가 나왔을때 앞에 마침표 하나와 함께 문자를 더해주면 됩니다.
- 4단계
  - 아무 생각 없이 풀면 index error가 날 것입니다. (문자열이 비어있거나 길이가 1일때 array[1]에 접근하면 문제가 생깁니다.)
  - 길이가 1인경우와 2이상인 경우에 따로 체크해주면 됩니다.
- 5단계
  - 주어진대로 구현하면 됩니다.
- 6단계 (거의 다 왔습니다!)
  - 역시 주어진대로 길이를 체크해주고, 마침표를 체크해줍니다. (제거 후에만 마침표를 체크합니다!)
- 7단계
  - 길이를 체크한 뒤 while문을 통해 조건에 만족할 때까지 계속 붙여주면 됩니다.
  
```python
# 2021 카카오 블라인드 채용 - 신규 아이디 추천
# 주어진대로 구현하면 된다.
def solution(new_id):
    answer = ''
    # 1단계
    new_id1 = new_id.lower()
    
    # 2단계
    new_id2 = ''
    for l in new_id1:
        if ord('a') <= ord(l) <= ord('z'):
            new_id2 += l
        if ord('0') <= ord(l) <= ord('9'):
            new_id2 += l
        if l in ['-', '_', '.']:
            new_id2 += l
    
    # 3단계
    new_id3 = ''
    cnt = 0
    for l in new_id2:
        if l == '.':
            cnt += 1
        else:
            if cnt >= 1:
                new_id3 += '.'
                new_id3 += l
                cnt = 0
            else:
                new_id3 += l
    
    # 4단계
    new_id4 = new_id3
    if len(new_id4) == 1:
        if new_id4 == '.':
            new_id4 = ''
    elif len(new_id4) >= 2:
        if new_id4[0] == '.':
            new_id4 = new_id4[1:]
        if new_id4[-1] == '.':
            new_id4 = new_id4[:-1]
    
    # 5단계
    new_id5 = new_id4
    if len(new_id5) == 0:
        new_id5 = 'a'
    
    # 6단계
    new_id6 = new_id5
    if len(new_id) >= 16:
        new_id6 = new_id6[:15]
        if new_id6[-1] == '.':
            new_id6 = new_id6[:-1]

    # 7단계
    new_id7 = new_id6
    if len(new_id6) <= 2:
        new_id7 = new_id6
        while True:
            if len(new_id7) == 3:
                break
            new_id7 += new_id6[-1]
            
    answer = new_id7
    return answer
```

### 비고