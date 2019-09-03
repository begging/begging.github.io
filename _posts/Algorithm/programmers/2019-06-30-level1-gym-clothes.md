---
layout: post
title: '[Level 1] Gym clothes'
comments: true
author: Terry Ryu
date:   2019-06-30 02:45:00 +0900
tags: [programmers-level1, python-set]
category: [Algorithm, Programmers]
---

- ## Question [link (Korean)](https://programmers.co.kr/learn/courses/30/lessons/42862)
<hr/>
- ## Answer

```Python3

def solution(n, lost, reserve):

    reserve_ = sorted(list(set(reserve) - set(lost)))
    lost_ = sorted(list(set(lost) - set(reserve)))

    for r in reserve_:
        for l in lost_:
            if l in [r-1, r+1]:
                lost_.remove(l)
                break

        if not lost:
            break

    answer =  n-len(lost_)

    return answer

```
