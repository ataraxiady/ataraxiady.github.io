---
layout: post
title:  "[Learning Evaluations - Interval Target] (Root Average Squared Error, Relative Error)"
subtitle:   
categories: dev
tags: ml
comments: true
header-img: 
---
<script type="text/javascript" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML">
</script>
Supervised model(target variable이 있는 모델)이 좋은 모델인지 아닌지 판단하는 방법에는 여러가지가 있다.  
앞으로 소개할 learning evaluations은 어떤 모델을 사용하는 것이 좋을지 판단해주는 지표들이다.  
다양한 지표들이 있기에 타겟의 유형별(Interval, Binary, Nominal)로 나누어 글을 써보려고 하는데 이 글은 `Interval 타겟` 의 learning evalutations이다.  
  
  
자세한 설명에 앞서 짤막한 요약은 아래 표와 같다.  
  
| Interval                                    | Binary                   | Nominal |
| :---: | :---: | :---: |
|RASE<br>Relative Error  | AUC<br>RASE<br>Misclassification Rate<br>F1 Score<br>Receiver Operating Characteristic Curve<br>Lift Curve<br>Kolmogorov-Smirnov Curve<br>Precision-Recall Curve | AUC<br>RASE<br>Misclassification Rate |

<!-- [Interval 타겟 바로가기](#interval-타겟)  
[Binary 타겟 바로가기](#binary-타겟)  
[Nominal 타겟 바로가기](#nominal-타겟)   -->

---
  
## Interval 타겟 Learning Evaluations
  
### 1. Root Average Squared Error(RASE)  
$$\sqrt{\frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y_i})^2}$$  
- $$y_i$$ 는 observed target value  
- $$\hat{y_i}$$ 는 predicted target value  
- n은 observation의 총 개수이다.  
- __RASE값이 1보다 작다면 좋은 모델이다__  
- 그러나 값이 완전 0인 것도 좋지않은데 값이 0이라는 것은 $$y_i$$ = $$\hat{y_i}$$을 의미하고 이는 모델이 overfitted 된 것이기 때문이다.  
  
  
### 2. Relative Error  
$$\frac{\sum_{i=1}^{n}(y_i - \hat{y_i})^2}{\sum_{i=1}^{n}(y_i - \bar{y_i}^2}$$  
- $$\bar{y_i}$$ 는 observed target mean  
- __Relative Error값이 1보다 작다면 좋은 모델이다__  
- 만약 relative error가 1이라면 predicted target value와 observed mean이 같은 것이다.  


