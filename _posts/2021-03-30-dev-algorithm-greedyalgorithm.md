---
layout: post
title:  "그리디 알고리즘이란 (Greedy Algorithm)"
subtitle:   
categories: dev
tags: algorithm
comments: true
header-img: 
---

## 그리디 알고리즘 (Greedy Algorithm)
- 항상 최적의 해를 구하는 동적 계획법과는 다르게 그리디 알고리즘은 현재 단계에서 선택할 수 있는 최적의 선택만을 하여 답을 구성해나가는 방식이다. 그러나 이 방식은 결론적으로 최적의 해를 구한다고 단정지을 수 는 없다.  
<img src="https://ataraxiady.github.io/assets/img/\dev\algorithm/greedyfail.png">
  
+ 그리디 알고리즘과 동적 계획법은 상호보완적인데 그리디 알고리즘은 __빠른 계산 속도__ 을 가지고 동적 계획법은 __최적의 해__ 를 구한다는 점에서 장점이 있다.
+ 그리디는 아래 두 가지 조건이 성립되어야 잘 작동할 수 있다.
- 탐욕스러운 선택 조건 (Greedy choice property) : 앞의 선택이 이후의 선택에 영향을 주지 않는 조건  
- 최적 부분 구조 조건(Optimal Substructure) : 문제에 대한 최종 해결 방법이 부분 문제에 대해서도 또한 최적 문제 해결 방법이다는 조건  
+ 그리디 알고리즘이 적용되는 대표적인 예시가 몇 가지 있다. 참고 사이트 두번째 링크에서 확인해볼 수 있다.  
1. 활동 선택 문제 (The Activity-Selection Problem)  
1. 분할가능 냅색 문제 (The Fractional Knapsack problem)  
  


---
##### 참고 사이트
<https://velog.io/@cyranocoding/%EB%8F%99%EC%A0%81-%EA%B3%84%ED%9A%8D%EB%B2%95Dynamic-Programming%EA%B3%BC-%ED%83%90%EC%9A%95%EB%B2%95Greedy-Algorithm-3yjyoohia5#:~:text=com%2Fgreedy.php-,Greedy%20Algorithms(%ED%83%90%EC%9A%95%EB%B2%95%2C%20%ED%83%90%EC%9A%95%20%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98),%ED%95%98%EB%8A%94%20%EB%AC%B8%EC%A0%9C%20%ED%95%B4%EA%B2%B0%20%EB%B0%A9%EC%8B%9D%EC%9D%B4%EB%8B%A4.>  
<https://www.zerocho.com/category/Algorithm/post/584ba5c9580277001862f188>  