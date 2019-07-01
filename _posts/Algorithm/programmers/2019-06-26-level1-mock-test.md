---
layout: post
title: '[Level1] Mock test'
comments: true
author: Terry Ryu
date:   2019-06-26 20:00:00 +0900
tags: [programmers-level1]
category: [Algorithm, Programmers]
---

- ## Question [link (Korean)](https://programmers.co.kr/learn/courses/30/lessons/42840)
<hr/>
- ## Answer 

```Python3

def solution(answers):

    if len(answers) > 10000:
        raise Exception('The size of answers should not be over 10000')
    
    gamblers =[(1,2,3,4,5),
               (2,1,2,3,2,4,2,5),
               (3,3,1,1,2,2,4,4,5,5)]
    
    len_recurs = [len(gambler) for gambler in gamblers]
    
    scores = [0]*len(gamblers)
    
    for i, a in enumerate(answers):

        if a not in [1,2,3,4,5]:
            raise Exception('answer should be in [1,2,3,4,5]')

        for j, gambler in enumerate(gamblers):
            if a == gambler[i%len_recurs[j]]:
                scores[j] += 1
    
    max_score = max(scores)

    answer = [i+1 for i, s in enumerate(scores) if s == max_score]

    # answer = [i[0]+1 for i in sorted(enumerate(scores), 
    #                                  key=lambda x:x[1],
    #                                  reverse=True)]

    return answer

```