---
title: "[Python] BOJ 11719번. 그대로 출력하기 2"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: Algorithm BOJ Implement Bronze
meta_keywords: 알고리즘,백준,파이썬,11719번
date: 2020-06-09 20:01:59 -0400
last_modified_at: 2020-06-09T20:01:59+08:00
---

# 11719번. 그대로 출력하기 2

### 문제 링크
- <https://www.acmicpc.net/problem/11719>{: target="\_blank"}

### 풀이 코드

```python
# 11719번. 그대로 출력하기 2


# ide에서는 안되는데 제출하니까 된다...
while True:
    try:
        print(input())
    except EOFError:
        break
```

### 비고