---
layout: post
title:  "DFS와 BFS(깊이 우선 탐색과 너비 우선 탐색)"
subtitle:   
categories: dev
tags: algorithm
comments: true
header-img: 
---

그래프 탐색의 대표적인 방법으로는 DFS와 BFS가 있다.  
그래프 탐색의 목적은 모든 정점을 한 번씩 방문한다는 것인데 위 두가지는 차이는 '어떤 순서로 방문할 것인가' 이다.  

<img src="https://ataraxiady.github.io/assets/img/dev/algorithm/dfsbfs.gif">

---
## DFS (깊이 우선 탐색)  
- DFS는 깊이 우선 탐색으로 __갈 수 있는 만큼 최대한 깊게, 더 이상 없을시 이전 정점으로 돌아가 탐색__ 을 하는 방법이다.  
- 모든 노드를 방문하고 싶을 경우 이 방법을 선택하고 BFS보다 간단하지만 속도는 BFS보다 더 느리다.  
- 재귀(방문 여부 검사를 꼭 해야함)나 스택을 사용한다.  

---

## BFS (너비 우선 탐색)  
- BFS는 너비 우선 탐색으로 __시작 정점으로부터 가까운 정점을 먼저 방문하고 멀리 떨어져있는 정점을 나중에 방문__ 하는 순회방법이다.  
- 두 노드 사이의 최단 경로 혹은 임의의 경로를 찾고 싶을 때 사용한다.  
- 큐(선입선출)를 사용한다.  
    


---
##### 참고
<https://yunyoung1819.tistory.com/86>  
<https://velog.io/@kjh107704/%EA%B7%B8%EB%9E%98%ED%94%84-BFS%EC%99%80-DFS>  

