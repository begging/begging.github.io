---
layout: post
title: '[Level 1] Kth number'
comments: true
author: Terry Ryu
date:   2019-06-27 20:00:00 +0900
tags: [programmers-level1, python-map]
category: [Algorithm, Programmers]
---

- ## Question: [link (Korean)](https://programmers.co.kr/learn/courses/30/lessons/42748)
<hr/>
- ## Answer

```Python3

def solution(array, commands):

	answer = []

	for command in commands:

		i = command[0]-1
		j = command[1]-1
		k = command[2]-1

		answer.append(sorted(array[i:j+1])[k])

	return answer

```
<hr/>
- ## Other Answer

```Python3

def other_solution(array, commands):
	return list(map(lambda x:sorted(array[x[0]-1:x[1]])[x[2]-1], commands))

```
