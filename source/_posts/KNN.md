---
title: "KNN"
author: "Young Jae Kim"
date: '2022-05-15'
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
# KNN (K-nearest neighbor)

### 출처:한국공학대학교 강지훈교수님 강의 中

### Classification

- 분류나 예측을 진행할때 나랑 가장 가까운 이웃 k개를 고려하겠다.

<나랑 가까운 이웃 한명이 검정색이면 검정색으로 판단>

![Untitled](images/knn/0.png)

<파란색의 가장 가까운 이웃을 확인해본 결과 검정색 이므로 파란색도 검정색으로 분류되었다.>

![Untitled](images/knn/1.png)

<K=3 일 경우 형광색 친구를 분류한다고 하였을때 이웃중 파란색이 2개 검정색이 한개이기 때문에 파란색으로 분류된다.

![Untitled](images/knn/2.png)

- 분류를 원하는 관측치의 주변 N개의 데이터(근접 이웃)을 골라서, 주변대세를 확인 (다수결의 원칙으로)

### Prediction

![Untitled](images/knn/3.png)

![Untitled](images/knn/4.png)

- 인접 K개의 데이터의 수치를 확인해줘서 그 데이터의 평균을 검은점의 예측치로 설정해준다.

### How to find optimal k?

### k의 결정

- k가 너무 큰 경우, KNN모델이 지나치게 일반화됨
- K가 너무 작은 경우,KNN 모델의 예측 결과의 분산이 큼
- 주로 이것저것 해보고 error이 가장 작은 k를 설정하여준다.

![Untitled](images/knn/5.png)

### 거리 척도의 결정

- 상황에 맞는 거리척도를 사용하여야 한다.
- 거리척도의 종류:Minkowski distance , Euclidean distance, Citi block distance, Mahalanobis distance, Correlation distance 등

# Distance

## 유클리디안 거리

![Untitled](images/knn/6.png)

- 가장 흔히 사용하는 거리측도
- 대응되는 x,y값 간 차이 제곱합의 제곱근으로써, 두 관측치 사이의 직선 거리를 의미함.

![Untitled](images/knn/7.png)

### 다차원 데이터에서도 마찬가지 이다.

![Untitled](images/knn/8.png)

# Manhattan Distance(격자 거리)

### 맨하탄은 블럭이 나누어져 있어 직선으로 갈 수가 없다.

![Untitled](images/knn/9.png)

### 직선거리가 아닌 격자거리.

- 격자:바둑판처럼 가로세로를 일정한 간격으로 직각이 되게 짠 구조나 물건.

![Untitled](images/knn/10.png)

- 각 좌표의 차이의 절댓값의 합

![Untitled](images/knn/11.png)

# Mahalanobis Distance

![Untitled](images/knn/12.png)

- 변수 내 분산,변수 간 공분산을 모두 반영하여 x,y,간 거리를 계산하는 방식⇒변수간 상관관계를 고려한 거리지표이다.
- 데이터의 공분산 행렬이 단위행렬인 경우는 유클리디안 거리와 동일함

공분산 행렬의 역행렬을 취했다는 것은 → 분산이 분모에 들어간다는 뜻 → 분산이 커지면 거리가 작아지고 , 분산이 작아지면 거리가 길어지고

### 마할라노비스거리가 제곱근이 취해져 있기 때문에 제곱근을 없앴다.

![Untitled](images/knn/13.png)

 

### 2차원 행렬로 비유를 했을시 ,  쭈욱 대입하면 아래의 식으로 나타난다

![Untitled](images/knn/14.png)

### y값에 0,0 을주고 대입하면 타원의 방정식이 나온다.

![Untitled](images/knn/15.png)

![Untitled](images/knn/16.png)

![Untitled](images/knn/17.png)

### 유클리디안 관점에서는 중앙점과 비교했을때, A가 더 멀다.

![Untitled](images/knn/18.png)

### 상관관계를 고려한 마할라노비스 거리로 보면 B가 더 멀다

![Untitled](images/knn/19.png)