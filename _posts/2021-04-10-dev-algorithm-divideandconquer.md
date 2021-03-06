---
layout: post
title:  "분할 정복이란 (Divide & Conquer)"
subtitle:   
categories: dev
tags: algorithm
comments: true
header-img: 
---

## 분할 정복 (Divide & Conquer)
- 주어진 문제를 둘 이상의 부분 문제로 나눈 뒤 각 문제에 대한 답을 재귀 호출을 이용해 계산하고, 각 부분 문제의 답으로부터 전체 문제의 답을 계산해 낸다.  
- 분할 정복이 일반적인 재귀 호출과 다른 점은 문젤르 한 조각과 나머지 전체로 나누는 대신 __거의 같은 크기의 부분 문제로 나눈다는 것__ 이다. 같은 작업일지라도 빠르게 해결할 수 있다는 장점을 가지고 있다.
  
분할 정복을 사용하는 알고리즘은 대게 세 가지 구성요소를 가지고 있다.   
1. 문제를 더 작은 문제로 분할하는 과정 (Divide)  
1. 각 문제에 대해 구한 답을 원래 문제에 대한 답으로 병합하는 과정 (Merge)  
1. 더이상 답을 분할하지 않고 곧장 풀 수 있는 매두 작은 문제 (Base case)  
  
문제에 이런 특성이 있어야 분할 정복을 사용할 수 있다  
1. 문제를 둘 이상의 부분으로 나누는 자연스러운 방법이 있다.  
1. 부분 문제의 답을 조합해 원래 문제의 답을 계산하는 효율적인 방법이 있다.  
  
- 절반으로 나누는 알고리즘이 큰 효율 저하를 불러오는 등 같은 문제라도 어떻게 분할하느냐에 따라 시간 복잡도 차이가 커지기도하는데 이렇게 중복 계산이 반복되며 시간을 소보하는 문제를 'Overlapping subproblems'라고 한다. 이는 동적 계획법을 고안하는 계기가 되기도 하는데 더 자세한 내용은 아래 링크에서 확인해볼 수 있다.  
<https://ataraxiady.github.io/dev/2021/03/22/dev-algorithm-dynamicprogrammingalgorithm/>  
  
    


---
##### 참고
알고리즘 문제 해결 전략1  
