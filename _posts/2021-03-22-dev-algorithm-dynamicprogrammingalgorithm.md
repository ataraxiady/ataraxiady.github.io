---
layout: post
title:  "동적계획법 (Dynamic Programming)"
subtitle:   
categories: dev
tags: algorithm
comments: true
header-img: 
---

## 동적계획법이란 (Dynamic Programming)
- 동적계획법이란 전체 문제를 subproblmes로 단순화하고 재귀적 구조를 활용하여 병합해나가며 전체 문제를 해결하는 방법이다.  
- 분할정복 알고리즘(Divide & Conquer)은 subproblems가 여러번 계산되지만 __동적계획법은 딱 한번만 계산하고 그 답을 배열에 저장해두기에(Memoization) 매번 다시 계산하는 불필요한 작업을 피한다.__  
- 중복 계산을 줄이기에 시간복잡도가 분할정복 알고리즘보다는 적다.  
  
1. 최적해를 구할 수 있도록 전체 문제를 작은 문제로 단순화한다
1. 최적해를 구할 수 있는 재귀적 구조를 찾는다
1. 일반적으로 Bottom-up방법으로 최적해를 계산한다 (작은 문제 해결방법으로 전체 문제 해결)
  
---

## 일반 재귀와 동적계획법 비교 (피보나치 계산)
  
일반적인 재귀를 사용한 피보나치 계산은 아래 코드(파이썬)와 같다.  

```python
n = int(input())

def fibo(n):
    if n == 0:
        return 0
    if n == 1:
        return 1
    if n >= 2:
        return fibo(n-1)+fibo(n-2)
print(fibo(n))
```
  
아래 이미지는 n이 6일때 호출되는 재귀이다. 보다시피 재귀가 중복되어 호출된다.    
<img src="https://ataraxiady.github.io/assets/img/dev/boj/10870_2.png">
  

동적계획법으로 생각을 해보자면  
- subproblems은 __F(n) = F(n-1) + F(n-2)__ 로 단순화 할 수 있다.  
- 그 후 Bottom-up 방식으로 코드를 구성한다.  
  
```python
n = int(input())

def fibonacci(n):
    # f(0)는 0이고 f(1)은 1이다. 이를 미리 배열에 저장해둔다.
    f = [0, 1]

    # n >= 2부터 주어진 값까지는 한번씩 계산하여 배열에 넣어준다.
    for i in range(2, n + 1):
        f.append(f[i - 1] + f[i - 2])
    return f[n]

print(fibonacci(6))
```