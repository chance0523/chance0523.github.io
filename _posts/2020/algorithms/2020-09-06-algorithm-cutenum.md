---
title: "[Python] BOJ 17294번. 귀여운 수"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-09-06 22:01:32 -0400
last_modified_at: 2020-09-06T22:01:32+08:00
---

# 17294번. 귀여운 수

### 문제 링크
- <https://www.acmicpc.net/problem/17294>{: target="\_blank"}

### 풀이 코드

```python
# 17294번. 귀여운 수


n = list(map(int, input()))

if len(n) == 1:
    print('◝(⑅•ᴗ•⑅)◜..°♡ 뀌요미!!')
else:
    d = n[0]-n[1]
    if len(n) == 2:
        print('◝(⑅•ᴗ•⑅)◜..°♡ 뀌요미!!')
    else:
        flag = True
        for i in range(1, len(n)-1):
            if n[i]-n[i+1] != d:
                print('흥칫뿡!! <(￣ ﹌ ￣)>')
                flag = False
                break
        if flag:
            print('◝(⑅•ᴗ•⑅)◜..°♡ 뀌요미!!')
```

### 비고