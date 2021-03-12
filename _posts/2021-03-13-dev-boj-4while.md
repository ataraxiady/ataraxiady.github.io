---
layout: post
title:  "백준(while문) 10952번, 10951번, 1110번 (파이썬)"
subtitle:   
categories: dev
tags: boj
comments: true
header-img: 
---

백준 4단계인 [while문](https://www.acmicpc.net/step/2) 문제들의 답을 모아두었습니다.  
큰 설명없이 코드만 달아두도록 하겠습니다.  


 
+ 문제 링크  
    - [10952번 (A+B -5)](https://www.acmicpc.net/problem/10952)  
    - [10951번 (A+B -4)](https://www.acmicpc.net/problem/10951)  
    - [1110번 (더하기 사이클)](https://www.acmicpc.net/problem/1110)  

---

### 10952번 (A+B -5)

```python
a,b = map(int,input().split())
while (a != 0 and b != 0):
    print(a+b)
    a, b = map(int, input().split())
```
  
###  10951번 (A+B -4)
```python
while True:
    try:
        a,b = map(int,input().split())
        print(a+b)
    except:
        break
```
  
### 1110번 (더하기 사이클)
```python
n = input()
if int(n) < 10:
    n = '0'+n
a = int(n[0])
b = int(n[1])
plus = a+b
splus = str(plus)
if plus < 10:
    splus = '0'+splus
new = n[1]+splus[1]
i = 1
while(n != new):
    a = int(new[0])
    b = int(new[1])
    plus = a + b
    splus = str(plus)
    if plus < 10:
        splus = '0' + splus
    new = new[1] + splus[1]
    i = i + 1
print(i)
```
  