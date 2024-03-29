---
title: "[Python] BOJ 1347번. 미로 만들기"
excerpt: '알고리즘'
comments: true

categories:
    - Algorithm
tags:
    - [알고리즘,백준,파이썬]
toc: true
toc_sticky: true
date: 2020-06-30 17:18:00 -0400
last_modified_at: 2020-06-30T17:18:00+08:00
---

# 1347번. 미로 만들기

### 문제 링크
- <https://www.acmicpc.net/problem/1347>{: target="\_blank"}

### 풀이 코드

```python
# 1347번. 미로 만들기


l = int(input())
maze = [['#' for i in range(200)] for i in range(200)]
step = list(input())
cury = 100
curx = 100
maze[cury][curx] = '.'
# y,x 임에 유의
direction = ['S', 'W', 'N', 'E']*50
dirIdx = 0
for i in range(l):
    if step[i] == 'R':
        dirIdx += 1
    elif step[i] == 'L':
        dirIdx -= 1
    else:  # 'F'
        if direction[dirIdx] == 'S':
            cury += 1
            maze[cury][curx] = '.'
        elif direction[dirIdx] == 'E':
            curx += 1
            maze[cury][curx] = '.'
        elif direction[dirIdx] == 'N':
            cury -= 1
            maze[cury][curx] = '.'
        else:  # 'W'
            curx -= 1
            maze[cury][curx] = '.'

yList = []
xList = []
for y in range(200):
    for x in range(200):
        if maze[y][x] == '.':
            yList.append(y)
            xList.append(x)
for y in range(min(yList), max(yList)+1):
    for x in range(min(xList), max(xList)+1):
        print(maze[y][x], end='')
    print()
```

### 비고