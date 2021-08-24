---
title: '[Python] Programmers. 2020 카카오 블라인드 - 문자열 압축'
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,프로그래머스,파이썬,카카오블라인드]
toc: true
toc_sticky: true
date: 2021-08-25 01:10:25 -0400
last_modified_at: 2021-08-25T01:10:25+08:00
---

# 2020 카카오 블라인드 채용 - 문자열 압축

### 문제 링크
- <https://programmers.co.kr/learn/courses/30/lessons/60057>{: target="\_blank"}

### 풀이 코드
- 문자열과 구현이 합쳐진 '카카오스러운' 문제입니다. 생각나는대로 구현하시면 됩니다.
- 1부터 주어지는 문자열 길이의 절반까지만 for문을 돌며 압축할 길이를 정합니다.
- 압축 할 수 있을 때 바로 압축하지 말고 `cnt`로 들고 있다가 한 번에 (숫자+압축문자열) 식으로 만들어주면 됩니다. 압축 할 수 없을때는 `0문자`가 아니라 `문자`로 만들어줘야하는 것에 주의해야합니다.
- for문을 돌며 문자열을 다 탐색 한 뒤 `cnt`가 남아있을 수 있습니다. (문자열이 `aaaabb`이고 2개 단위로 압축하면 `2aa`까지 만들어진 뒤 `bb`는 아직 문자열에 더해져있지 않은 상태로 남아있겠죠?) 남아있는 cnt를 동일한 방식으로 처리하면 됩니다.
- 압축 단위마다 최소값을 갱신해주면 됩니다.

```python
# 2020 카카오 블라인드 채용 - 문자열 압축
def solution(s):
    answer = len(s)
    if len(s) == 1:
        return 1
        
    for i in range(1, len(s) // 2 + 1):
        cnt = 1 # 0이 아니라 1부터 (1a 같은 경우는 a와 동일!)
        cur = ''
        temp = s[:i]
        for j in range(i, len(s), i):
            if temp == s[j:j+i]:
                cnt += 1
            else:
                if cnt == 1: # 압축 할 수 없을 때
                    cur += temp
                else: # 압축 할 수 있을 때
                    cur += str(cnt) + temp
                cnt = 1
                temp = s[j:j+i] # 이 문자열부터 다시
                
        if cnt == 1: # 남은 것들 flush
            cur += temp
        else:
            cur += str(cnt) + temp
        answer = min(answer, len(cur)) # 길이 갱신
                    
    return answer
```

### 비고