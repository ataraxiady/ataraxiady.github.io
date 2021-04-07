---
layout: post
title:  "스택 (Stack)"
subtitle:   
categories: dev
tags: algorithm
comments: true
header-img: 
---

## 스택이란 (Stack)
- 같은 구조와 같은 크기의 자료들을 정해진 방향으로만 쌓을 수 있고 __후입선출(LIFO)__ 형식으로 입출력이 일어나는 자료구조이다.
- 제일 먼저 입력된 데이터가 맨 아래 쌓이고 가장 최근에 입력된 데이터가 가장 위에 쌓이는 구조이다.
- 삽입 연산은 __Push연산__ 이라 하고 삭제 연산은 __pop 연산__ 이며 둘다 사용이 쉽다.
- 비어있는 스택에서 원소를 추출하는 것은 Stack underflow이고 스택이 넘치는 경우 stack overflow라고 말한다.
  
<img src="https://ataraxiady.github.io/assets/img/dev/algorithm/stack.png">
  
## 장점과 단점 
- 장점 : 데이터의 삽입과 삭제가 빠르다  
- 단점 : 탐색을 하려면 원소를 하나하나 꺼내서 옮겨야하고 맨 위의 원소만 접근 가능하다  
- 재귀 알고리즘이나 역추적을 해야할 경우(실행취소) 유용하게 사용할 수 있다  
  

---
##### 참고 사이트
C언어로 쉽게 풀어쓴 자료구조  
<https://devuna.tistory.com/22#:~:text=%EC%8A%A4%ED%83%9D(stack)%EC%9D%B4%EB%9E%80%20%EC%8C%93%EC%95%84%20%EC%98%AC%EB%A6%B0%EB%8B%A4,%EC%9D%98%20%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0%EB%A5%BC%20%EB%A7%90%ED%95%9C%EB%8B%A4.&text=%EC%8A%A4%ED%83%9D%EC%9D%80%20%EC%9C%84%EC%9D%98%20%EC%82%AC%EC%A7%84,%ED%86%B5%ED%95%B4%EC%84%9C%EB%A7%8C%20%EC%A0%91%EA%B7%BC%ED%95%A0%20%EC%88%98%20%EC%9E%88%EB%8B%A4. >  
<https://velog.io/@choiiis/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-%EC%8A%A4%ED%83%9DStack%EA%B3%BC-%ED%81%90Queue>