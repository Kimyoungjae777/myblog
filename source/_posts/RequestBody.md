---
title: "RequestBody vs RequestParam"
author: "Young Jae Kim"
date: '2022-12-28'
categories: 
- Development
- 기본개념
tags:
- Development
- 기본개념

---
# RequestBody,RequestParam,ModelAttribute 의 차이

컨트롤러에서 데이터를 인자에 할당하는 대표적인 방법으로는 @RequestBody 와 @RequestParam 이 있다. 

![Untitled](images/RequestBody/0.png)

### form 태그로 데이터를 전달

먼저, 기본적인 형태인 <form> 태그를 통해서 데이터를 전송해보자.

![Untitled](images/RequestBody/1.png)

- 아래와 같이 데이터를 전송하여 컨트롤러에서 @RequestBody 를 이용하여 데이터를 받아보겠다.

![Untitled](images/RequestBody/2.png)

### @RequestBody

- 클라이언트가 전송하는 JSON 형태의 Http Body 내용을 MessageConverter 를 통해 Java Object로 변환시켜주는 역할을 합니다 .
- 값을 주입하지 않고 값을 변환 시키므로, 변수들의 생성자, Getter,Setter가 없어도 정상적으로 할당된다.

** 우리가 입력한 ‘jun’ 이라는 이름과 ‘13’ 이라는 나이가 잘 전달이 되었지만 단지 ‘name=jun&age=13’ 이라는 string 으로 전달되어 전달된 데이터를 사용하기엔 불편함이 있다.

그렇다면 이번엔 @RequestParam 으로 받아보자

![Untitled](images/RequestBody/3.png)

### @RequestParam

- 1개의 HTTP 요청 파라미터를 받기 위해 사용한다. @RequestParam 필수 여부가 true 이기 때문에 , 기본적으로 반드시 해당 파라미터가 전송되어야 한다. 전송되지 않으면 400 error를 유발할 수 있으며, 반드시 필요한 변수가 아니라면 required=false로 설정해줘야 한다.

** @RequestBody 로 데이터를 받을때는 메서드의 변수명이 상관이 없었지만, @RequestParam 으로 데이터를 받을때는 데이터를 저장하는 이름으로 메서드의 변수명을 설정해주어야 한다 

결과적으로 jun 이라는 이름이 잘 전달이 되었고, 이번엔 name 이라는 변수에 할당이 되어 사용하기에도 용이하다.