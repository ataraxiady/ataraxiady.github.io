---
layout: post
title:  "백트래킹 알고리즘이란 (Backtracking Algorithm)"
subtitle:   
categories: dev
tags: algorithm
comments: true
header-img: 
---

## 백트랙킹 알고리즘 (Backtracking Algorithm)  
- 백트래킹은 여러 개의 솔루션을 가진 문제에서 __조건을 만족하는 모든 솔루션을 체크__ 하는 알고리즘이다.  
- 솔루션을 하나씩 체크하며 조건에 맞지 않는 솔루션은 삭제하는 과정을 거친다.  
- 재귀를 사용하거나 스택을 통한 DFS를 사용할 수 있다.  

+ 백트래킹 원리  
1. 어떤 노드의 유망성을 점검 후  
1. 유명하지 않으면 가지치기(Pruning)  
1. 해당 노드의 부모 노드로 되돌아간 후 다른 자손 노드를 검색한다.(이를 통해 시간을 감축)  
  
  
<!-- ## 대표적인 예 (N-Queens)
구글링을 통해 백트래킹 정보글들을 봤을 때 모두들 N-Queens문제를 백트랙킹을 사용하는 대표적인 문제로 뽑으셨다.  
마침 백준 백트래킹 단계에 N-Queens 문제가 있어서 그에 대한 해설을 아래 첨부하도록하겠다.  
  
[백준 9663 N-Queen](https://www.acmicpc.net/problem/9663)  
   -->
---
##### 참고 사이트
<https://www.geeksforgeeks.org/backtracking-algorithms/>  
<https://jeongdowon.medium.com/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-backtracking-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-13492b18bfa1>  
<https://velog.io/@leobit/DFS-BFS-%EB%B0%B1%ED%8A%B8%EB%9E%98%ED%82%B9Backtracking>  
<https://thd0011.tistory.com/19>  