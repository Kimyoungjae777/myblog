---
title: "Form 태그로 데이터 주고 받기"
author: "Young Jae Kim"
date: '2022-12-29'
categories: 
- Development
- 기본개념
tags:
- Development
- 기본개념

---
# Form 태그로 데이터 주고 받기

🚩 1. Form html 을 form 태그로 꾸며준다

     2. form 의 name을 Dto 에 만들어준다

     3. action 을 통해 form 태그와  controller 를 연결해주고 

        데이터를 받아온다. 

### Form 태그

![Untitled](images/Form/0.png)

 

- **name:**form 태그에 name 에 이름을 정해주고 이 이름과 , DTO의 이름을 맞추어준다
- **action:** 어떤 컨트롤러와 연결해줄지 정해준다

### Controller

![Untitled](images/Form/1.png)

- GetMapping 으로 일반 페이지를 조회시켜주고
- PostMapping 으로 데이터를 전송하였을떄 받아주는 역할을 한다.
- DTO 에 있는것을 가져와서 출력.

### DTO

![Untitled](images/Form/2.png)

- form 의 name 과 맞추어 주고 생성자로 name 과 매칭시켜 DTO에 저장시켜준다.
- 그리고 그것을 출력할 수 있게 to string 을 만들어준다.

![Untitled](images/Form/3.png)

![Untitled](images/Form/4.png)