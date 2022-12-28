---
title: "Spring Mvc 란"
author: "Young Jae Kim"
date: '2022-12-28'
categories: 
- Development
- 기본개념
tags:
- Development
- 기본개념

---
# Spring MVC 에 대해 설명해주세요

- MVC는 Model,View,Controller의 약자이며, 각 레이어간 기능을 구분하는데 중점을 둔 디자인 패턴입니다.
- Model은 데이터관리 및 비즈니스 로직을 처리하는 부분이며,(DAO,DTO,Service 등)
- View는 비즈니스 로직의 처리 결과를 통해 유저 인터페이스가 표현되는 구간입니다.(html,jsp,thymeleaf,mustache 등 화면을 구성하기도 하고, Rest API로 서버가 구현된다면 JSON 응답으로 구성되기도 한다)
- Controller는 사용자의 요청을 처리하고 Model 과 View를 중개하는 역할을 합니다. model 과 view 는 서로 연결되어 있지않기 떄문에 Controller 가 사이에서 통신매체가 되어줍니다.

![Untitled](images/SpringMvc/0.png)

# MVC 패턴의 흐름

![Untitled](images/SpringMvc/1.png)

- **DispatcherServeket**: 클라이언트에게 요청을 받아 응답까지의 MVC 처리과정을 통제한다.
- **HandlerMapping**:클라이언트의 요청 URL을 어떤 Controller가 처리할지 결정한다.
- **HandlerAdapter:HandlerMapping**에서 결정된 핸들러 정보로 해당 메소드를 직접 호출해주는 역할을한다.
- **ViewResolver**:Controller의 처리 결과(데이터)를 생성할 view 를 결정한다.

1. 클라이언트는 URL을 통해 요청을 전송한다.
2. 디스패치 서블릿은 핸들러 매핑을 통해 해당 요청이 어느 컨트롤러에게 온 요청인지 찾는다.
3. 디스패치 서블릿은 핸들러 어댑터에게 요청의 전달을 맡긴다. 
4. 핸들러 어댑터는 해당 컨트롤러에 요청을 전달한다.
5. 컨트롤러는 비즈니스 로직을 처리한 후에 반환할 뷰를 찾는다.
6. 디스패치 서블릿은 뷰 리졸버를 통해 반환할 뷰를 찾는다.
7. 디스패치 서블릿은 컨트롤러에서 뷰에 전달할 데이터를 추가한다. 
8. 데이터는 추가된 뷰를 변환한다.