
---
title: "넘파이 기초"
author: "Young Jae Kim"
date: '2022-03-23'
category: numpy
--- 

# Numpy 라이브러리 불러오기 


```python
import numpy as np
print(np.__version__)

```

    1.21.5
    

# 배열로 변환 
-  1부터 10까지의 리스트를 만든다.
- Numpy 배열로 변환해서 저장한다. 



```python
temp=[1,2,3,4,5,7,8,9,10]  #지금은 리스트다
arr=np.array(temp)
print(arr)
type(arr)#array 로 바뀌었다.


```

    [ 1  2  3  4  5  7  8  9 10]
    




    numpy.ndarray



- arr 배열 숫자 5 출력 


```python
arr[4] # 인덱싱 파이썬은 0번째 부터!!
arr[4:8]
```




    array([5, 7, 8, 9])



- Numpy를 이용하여 기초통계 함수를 사용한다


```python
print(np.mean(arr))
print(np.sum(arr))
print(np.median(arr))
print(np.std(arr))
```

    5.444444444444445
    49
    5.0
    3.02254900194121
    


```python

```

사칙연산


```python
math_score=[90,80,88]
english_score=[80,70,90]

total_score=math_score+english_score
total_score# 더해지는게 아니라 붙혀지는 형태로 나옴 

```




    [90, 80, 88, 80, 70, 90]




```python

```


```python
math_score=[90,80,88]
english_score=[80,70,90]

math_arr=np.array(math_score)
english_arr=np.array(english_score)
totalscore=math_arr+english_arr
totalscore


```




    array([170, 150, 178])




```python
np.min(totalscore)
np.max(totalscore)
```




    178




```python
# 덧셈
print("덧셈:",np.add(math_arr,english_arr))
print("뺄셈:",np.subtract(math_arr,english_arr))
print("곱셈:",np.multiply(math_arr,english_arr))
print("뺄셈:",np.divide(math_arr,english_arr))
print("거듭제곱:",np.power(math_arr,english_arr))
```

    덧셈: [170 150 178]
    뺄셈: [10 10 -2]
    곱셈: [7200 5600 7920]
    뺄셈: [1.125      1.14285714 0.97777778]
    거듭제곱: [0 0 0]
    

## 배열의 생성 
- 0차원부터 3차원으로 생성하는 방법


```python
temp_arr=np.array(20)
print(temp_arr)
print(type(temp_arr))
print(temp_arr.shape)

```

    20
    <class 'numpy.ndarray'>
    ()
    


```python
#1차원 배열
temp_arr=np.array([1,2,3])
print(temp_arr)
print(type(temp_arr))
print(temp_arr.shape)  # 3개의 사이즈를 가지고 있는 1차원 배열이다.
print(temp_arr.ndim) #차원 출력

```

    [1 2 3]
    <class 'numpy.ndarray'>
    (3,)
    1
    


```python
# 2차원 배열
temp_arr=np.array([[1,2,3],[4,5,6]])
print(temp_arr)
print(type(temp_arr))
print(temp_arr.shape)  # 2x3 배열
print(temp_arr.ndim) #차원 출력
```

    [[1 2 3]
     [4 5 6]]
    <class 'numpy.ndarray'>
    (2, 3)
    2
    


```python
# 3차원 배열
temp_arr=np.array([[[1,2,3],[4,5,6],[1,2,3],[4,5,6]]])
print(temp_arr)
print(type(temp_arr))
print(temp_arr.shape)  # 2x3 배열
print(temp_arr.ndim) #차원 출력
```

    [[[1 2 3]
      [4 5 6]
      [1 2 3]
      [4 5 6]]]
    <class 'numpy.ndarray'>
    (1, 4, 3)
    3
    


```python
temp_arr=np.array([1,2,3,4],ndmin=2)
print(temp_arr)
print(type(temp_arr))
print(temp_arr.shape)  
print(temp_arr.ndim) 
```

    [[1 2 3 4]]
    <class 'numpy.ndarray'>
    (1, 4)
    2
    

# 소숫점 정렬


```python
temp_arr=np.trunc([-1.23,1.23])
temp_arr #소숫점이 절삭됨


```




    array([-1.,  1.])




```python
temp_arr=np.fix([-1.23,1.23])
temp_arr #소숫점이 절삭됨
```




    array([-1.,  1.])




```python
temp_arr=np.around([-1.23789,1.23789],4) #4는 자릿수 파라미터
temp_arr #소숫점이 반올림됨
```




    array([-1.2379,  1.2379])




```python
temp_arr=np.floor([-1.23789,1.23789]) #4는 자릿수 파라미터
print(temp_arr) #소숫점이 반올림됨
print(type(temp_arr))
```

    [-2.  1.]
    <class 'numpy.ndarray'>
    


```python
temp_arr=np.ceil([-1.23789,1.23789]) #4는 자릿수 파라미터
print(temp_arr) #소숫점이 반올림됨
```

    [-1.  2.]
    


```python

```

# 배열을 생성하는 다양한 방법들


```python
# arrange
temp_arr=np.arange(1,9,3) # 숫자 범위 지정해주고 세번째 파라미터는 step 을 의미 
temp_arr
```




    array([1, 4, 7])




```python
zero_arr=np.zeros((2,3))
print(zero_arr)
print(type(zero_arr))
print(zero_arr.ndim)  
print(zero_arr.shape) 
print(zero_arr.dtype)
```

    [[0. 0. 0.]
     [0. 0. 0.]]
    <class 'numpy.ndarray'>
    2
    (2, 3)
    float64
    


```python
temp_arr=np.ones((2,6))
temp_res_arr=temp_arr.reshape(3,4) #파라미터에 -1 을넣어주면 알아서 계산이된다

print(temp_res_arr)
print(type(temp_res_arr))
print(temp_res_arr.ndim)  
print(temp_res_arr.shape) 
print(temp_res_arr.dtype)

```

    [[1. 1. 1. 1.]
     [1. 1. 1. 1.]
     [1. 1. 1. 1.]]
    <class 'numpy.ndarray'>
    2
    (3, 4)
    float64
    

# numpy 조건식! 
- np.where


```python
temp_arr=np.arange(10)
temp_arr
```




    array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
# 5보다 작은 값은 원래값으로 변환
# 5보다 큰값은 원래값 * 10
# 조건식이 하나만 필요할때 np.where
np.where(temp_arr<5,temp_arr,temp_arr*10)
```




    array([ 0,  1,  2,  3,  4, 50, 60, 70, 80, 90])




```python
# 0~100 까지의 배열 만들고 , 50보다 작은 값은 *10
temp_arr=np.arange(100)
np.where(temp_arr<50,temp_arr,temp_arr*10) # 두번쨰 파라미터 조건식에 만족x ~다 세번째 파라미터 조건식에 맞으면  ~다
```




    array([  0,   1,   2,   3,   4,   5,   6,   7,   8,   9,  10,  11,  12,
            13,  14,  15,  16,  17,  18,  19,  20,  21,  22,  23,  24,  25,
            26,  27,  28,  29,  30,  31,  32,  33,  34,  35,  36,  37,  38,
            39,  40,  41,  42,  43,  44,  45,  46,  47,  48,  49, 500, 510,
           520, 530, 540, 550, 560, 570, 580, 590, 600, 610, 620, 630, 640,
           650, 660, 670, 680, 690, 700, 710, 720, 730, 740, 750, 760, 770,
           780, 790, 800, 810, 820, 830, 840, 850, 860, 870, 880, 890, 900,
           910, 920, 930, 940, 950, 960, 970, 980, 990])



- np.select



```python
temp_arr=np.arange(10)
temp_arr
condlist=[temp_arr>5,temp_arr<2]
choielist=[temp_arr*2,temp_arr+100]
np.select(condlist,choielist,default=temp_arr)


# 5보다 큰 값은 곱하기 2 , 2보다 작은 값은 더하기 100
# broadcasting 확인해보기
```




    array([100, 101,   2,   3,   4,   5,  12,  14,  16,  18])




