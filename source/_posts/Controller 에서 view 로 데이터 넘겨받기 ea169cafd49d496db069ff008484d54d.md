---
title: "컨트롤러에서 뷰로 데이터를 넘기는 원리"
author: "Young Jae Kim"
date: '2022-11-17'
output:
  html_document:
    keep_md: true
categories: 
- Development
- 기본개념
tags:
- Development
- 기본개념

---

# Controller 에서 view 로 데이터 넘겨받기

### 화면 처리( controller 에서 view 단으로 넘어가는 원리)

![Untitled](images/controllerToView/1.png)

**addAttribute 메서드** : 해당 메서드를 이용하여, 화면으로 데이터를 전달할 수 있다. 메서드의 인자로는 이름(String name), 값(Object value)을 전달한다. 웬만해서는 이름과 값을 동일하게 지정하는 것이 좋다.

HTML에서는 ${} 표현식을 이용하여 전달받은 데이터에 접근할 수 있다.

thymeleaf를 이용하여 전달받은 데이터 값을 화면에 출력해보자 

test.html 코드를 다음과 같이 변경한다.   

- ${} 안에  이름을 쓰면, 값이 출력되어진다.

![Untitled](images/controllerToView/2.png)

![Untitled](images/controllerToView/3.png)

**8080 포트**: WAS(WebApplicationServer) 에 해당하는 톰캣의 기본 포트이다. 스프링부트에서 WAS는 기본적으로 내장되어 있는 톰캣을 사용하며, [application.properties](http://application.properties) 에서 server.port 속성을 이용해서 원하는 포트로 지정 가능하다.

**/board/test**: openBoardWrite 메서드와 매핑된 URL을 의미한다. 만약 매핑되지 않은 URL을 호출하는 경우에는 404 에러가 발생한다. 

404에러는 “서버에서 사용자의 요청 URL을 찾을수 없음” 을 의미한다. HTTP 상태코드(Status code) 를 확인해보면 종류별로 나와있다. 

