---
title: "[Python] BOJ 2417번. 정수 제곱근"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-08-18 19:44:22 -0400
last_modified_at: 2020-08-18T19:44:22+08:00
---

# 2417번. 정수 제곱근

### 문제 링크
- <https://www.acmicpc.net/problem/2417>{: target="\_blank"}

### 풀이 코드

```python
# 2417번. 정수 제곱근


n = int(input())
tempRoot = n**0.5  # 제곱근

if(tempRoot-int(tempRoot) == 0):  # 정수라면
    print(int(tempRoot))

else:
    print(int(tempRoot)+1)
```

### 비고