---
layout: post
title:  "[R] 랜덤포레스트 에러 - The response has five or fewer unique values.  Are you sure you want to do regression?"
subtitle:   
categories: dev
tags: datamining
comments: true
header-img: 
---
## 랜덤포레스트(Random Forest) 에러

어느때와 다름없이 과제를 하고 있는 나.  
오늘은 랜덤포레스트 실습을 하고 있었다.  

교수님이 하란대로 잘 따라한 코드는 아래와 같다.  

```r
model_random1 <- randomForest(is_canceled ~ lead_time+market_segment+previous_cancellations+booking_changes+deposit_type+days_in_waiting_list+required_car_parking_spaces+total_of_special_requests, data=train, ntree=250, mtry=sqrt(8))
```
  
근데 아래와 같은 에러를 마주쳤다.  
`The response has five or fewer unique values.  Are you sure you want to do regression?`  
구글링해보니 Response variable, 즉 target을 factor로 바꾸어주어야한다.  

참고한 글에 따르면 이유는 다음과 같다.  
(영어를 직역한 것 뿐이고, R과 데이터마이닝에 얕은 지식을 가지고있기에 적당히 참고만 해주세요...ㅠ)  
  
> 랜덤포레스트는 reponse variable 타입에 기반하여 모델을 만드는 CART모델이기 때문이다.  
> 따라서 R에서는 랜덤 포레스트 실행 전, 랜덤포레스트에게 regresion 대신 classification을 실행하라고 명령하라고 미리 말해야한다.  

### 해결책

따라서 랜덤포레스트 돌리기 전에 factor로 바꾸는 코드를 추가해주면 된다.  

```r
train$is_canceled <- as.character(train$is_canceled)
train$is_canceled <- as.factor(train$is_canceled)

model_random1 <- randomForest(is_canceled ~ lead_time+market_segment+previous_cancellations+booking_changes+deposit_type+days_in_waiting_list+required_car_parking_spaces+total_of_special_requests, data=train, ntree=250, mtry=sqrt(8))
```

---

###### 마무리 및 사담
한국어를 섞어 구글링을 했음에도 불구하고 한국어 자료가 잘 나오지않길래 적는 글.  
영어자료도 무조건 읽으셔야하지만 그래롣 한국어 자료를 찾는 이들에게 모쪼록 도움이 되기를!   

###### 참고문헌
+ <https://discuss.analyticsvidhya.com/t/what-does-the-warning-the-response-has-five-or-fewer-unique-values-while-building-random-forest-mean/6442>