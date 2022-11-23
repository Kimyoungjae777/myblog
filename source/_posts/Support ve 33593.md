---
title: "Support vector machine"
author: "Young Jae Kim"
date: '2022-03-15'
output:
  html_document:
    keep_md: true
categories:
- Machinelearning
- 알고리즘
tags:
- Machinelearning
- 알고리즘


---


# Support vector machine

출처:한국공학대학교 경영학과 강지훈 교수님 강의. 中

## 분류에 대한 수적 표현에 대해 먼저 알아 보자.

- 학습 데이터 X(독립변수),Y(종속변수)가 있을 때 (i=1,2,3,4,5 ....데이터의 갯수)    Y⇒{-1,1} (두 개의 클래스를 의미)

![Untitled](/images/support/Untitled.png)

⇒ 경우에 따라서, 클래스를 1과 -1 로 나눔

Y(정답) * F(x)(예측한 정답) >0 라는 것은 제대로 분류된 형태 ( 같은 부호끼리 곱하면 양수인 경우니까)

## 선형 분할(Linear Classifier)

![Untitled](/images/support/Untitled%201.png)

f(x)=  W transpose X  + b  (선형조합, 각각의 항들이 더하기로 이루어진 조합.)

- 선형분할은 직선으로 나누는 것 (2차원이건 3차원이건 그 이상이건 상관 없음)
- b(bias) Y 절편을 의미
- W는 직선의 기울기

## 선형 분할 가능

![Untitled](/images/support/Untitled%202.png)

## 더 나은(최적) 분류를 위한 초평면(Hyperplane)→선 보다 더 큰 차원

![Untitled](/images/support/Untitled%203.png)

 

## 어떤 선이 좋은 판별선일까?

최적화→좋은 것 을 극대화 시키고 나쁜 것 을 극소화 시키는 것

 분류에서의 최적화→ 잘 안나뉘는것 , 잘 나뉘는 것 

![Untitled](/images/support/Untitled%204.png)

- 나중에 Testing data 를 돌렸을때,  가장 좋게 나누는 직선은 절반이다. 왜냐면 Test data 가 어떻게 들어올지 모르는 것 이기때문에 , 아슬아슬하게 나눈것 보다, 확실히 절반으로 나누는것이 좋다.

## 초평면 찾기.

- 2개의 class가 선형으로 구분 가능한 경우,
- class1과 class2를 구분할 수 있는 선의 종류는 무수히 많음
- 두 영역을 어떻게 나누는 것이 가장 적절한가?
    
    ![Untitled](/images/support/Untitled%205.png)
    
    ## 최적의 분할 초평면 찾기.
    
    c는 선형분할의 각 클래스별 거리 각 클래스별 거리를 합친것을 우리는 Margin 이라고 한다.  
    
    Margin=2c를 최대화 하는, w T x +b=0 의 직선을 찾아야 하는것 이다.
    
- Marign 을 최대화 시키는 초평면이 최적
- “Learning Theory” 에 따르면, Marigin을 최대화 시키는 초평면이 일반화 오류가 가장 낮게 나타남(Test data 에서도 좋은 점수가 나온다)
- Margin:초평면과 가장 근접한 각 클래스 관측치와의 거리의 합.

![Untitled](/images/support/Untitled%206.png)

 

## 기하학적인 Margin

![Untitled](/images/support/Untitled%207.png)

## Margin 수식 유도 1(일반적인 방법)

![Untitled](/images/support/Untitled%208.png)

## 마진 수식 유도 2(고등학교때 배운 방법 응용.

점과 선 사이의 거리

거리 d 가 2개이니까 2/||W||

![Untitled](/images/support/Untitled%209.png)

## 마진을 최대화 해보자 .(최적화)

- ||w|| 가 분모에 있기 때문에 결국 ||w|| 를 최소화 해주는것 이 2/||w|| 를 최대화 해주는거랑 같다고 할 수 있다
- 우리는 결국 w 값을 최소화 시켜주는것이 목적이기 때문에 제곱을 취해주든 상수를 곱해주는 상관이 없다

![Untitled](/images/support/Untitled%2010.png)

## 마진을 최대화 해보자 .(최적화)

- s.t→제약사항⇒ Yi(실제답) * (w*Xi +b)→모델답)  이 1보다 커야 한다. ⇒  올바르게 분류가 되는 조건.

- convex Optimization = 최적의 해가 항상 1개 존재하는 함수

![Untitled](/images/support/Untitled%2011.png)

- Quadraitc(2차) 목적함수와 선형 제약조건  (+로 변수 조합) 이 존재

![Untitled](/images/support/Untitled%2012.png)

![Untitled](/images/support/Untitled%2013.png)

## 마진을 최대화 해보자 .(최적화)

- Lagrange Multiplier(수학적 기법) ⇒ 제약조건을 최적화조건에 녹여버리는 기법.

![Untitled](/images/support/Untitled%2014.png)

## 라그랑쥬를 다 풀고 나면 판별식이 나온다.

-Xi tranpose X ( 학습데이터와 분류할 데이터의 내적)

![Untitled](/images/support/Untitled%2015.png)

## SVM(지지벡터머신)의 의미 정리

- 판별식에 서포트벡터만 사용하기 때문에 아웃라이어에 대한 영향을 안 받음(KKT 조건으로 걸러냄)
- KNN 또한 이웃을 확인하는 개수인 K의 한계가 있어서 어느 elbow point 를 지나치면 정확도가 떨어진다. → 비슷한 원리 ⇒ svm 또한 분류를 유효하게 하기위해서 support verctor 만 이용해준다.

![Untitled](/images/support/Untitled%2016.png)

## 만약에 선형으로 완벽히 나눠지지 않는 데이터라면

- 테스트데이터 에게는 위의 모델 보다 아래 모델이 더 좋을 것 으로 보인다. 하지만 SVM 의 제약조건에는 트레인데이터가 완벽하게 나누어져야 한다는 제약 조건이 걸려있다. 어떻게 하면 좋을까?

.

![Untitled](/images/support/Untitled%2017.png)

## 여유를 주자(Slack Variable for “Soft Margin”)

- error ⇒ 잘못 분류할 확율

![Untitled](/images/support/Untitled%2018.png)

## Soft Margin SVM

![Untitled](/images/support/Untitled%2019.png)

## Non-linear SVM

![Untitled](/images/support/Untitled%2020.png)

## 커널의 종류

![Untitled](/images/support/Untitled%2021.png)

## 커널의 종류에 따라 분할 경계

![Untitled](/images/support/Untitled%2022.png)