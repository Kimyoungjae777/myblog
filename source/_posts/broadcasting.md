---
title: "pandas 의 broadcastiong "
author: "Young Jae Kim"
date: '2022-03-16'
category: 데이터분석
---


# 판다스의 broadcastiong

참조:[(16) broadcastiong과 연산 | 판다스(pandas) 기본강의 #03 - YouTube](https://www.youtube.com/watch?v=iZ6v1DSmrHU)

- 넘파이의 연산.

→행과 열이 같아야 연산이 가능하다

![Untitled](/images/broadcastiong/Untitled.png)

- 3x3 행렬과 1x3 행렬의 곱이 위의 처럼 연산이 같아지는갓 1 행이 2행과 3행과 같다고 생각하고 하는 연산을 broadcastiong 라고 한다

![Untitled](/images/broadcastiong/Untitled%201.png)

★ numpy 와 pandas 의 차이 ★

numpy 는 저 행렬들의 자리가 중요하지만, pandas 는 index 와 columns 를 기준으로 라벨링을 기준으로 연산을 해준다.

![Untitled](/images/broadcastiong/Untitled%202.png)

- 라벨이 전부 다르기 때문에 전무 NaN 값이 나온다

![Untitled](/images/broadcastiong/Untitled%203.png)

![Untitled](/images/broadcastiong/Untitled%204.png)

![Untitled](/images/broadcastiong/Untitled%205.png)

이게 default 고 , 축 바꿔서 실행할 수 있다.  1차원이기 때문에 전치 행렬 개념이 없다.  

![Untitled](/images/broadcastiong/Untitled%206.png)

axis=0 일때

![Untitled](/images/broadcastiong/Untitled%207.png)

# # 실습

![Untitled](/images/broadcastiong/Untitled%208.png)

![Untitled](/images/broadcastiong/Untitled%209.png)

![Untitled](/images/broadcastiong/Untitled%2010.png)

![Untitled](/images/broadcastiong/Untitled%2011.png)