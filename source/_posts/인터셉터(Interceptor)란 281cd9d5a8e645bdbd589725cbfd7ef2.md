---
title: "interceptor (인터셉터)"
author: "Young Jae Kim"
date: '2022-08-06'
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
![Untitled](images/interceptor/interceptor.png)

# 인터셉터(Interceptor)란?

인터셉터는 이름 그대로 “무언가를 가로챈다” 라는 의미를 가집니다.

인터셉터는 컨트롤러의 url에 접근하는 과정에서 무언가를 제어할 필요가 있을때 사용됩니다.

정확히는 컨트롤러에 접근하기 전과 후로 나뉘는데, 

예를들어 회원제로 이루어지는 시스템이 있다고 가정했을 때, 로그인이나 계정의 권한과 관련된 처리등을 인터셉터를 이용해서 더욱 효율적으로 처리할 수 있습니다. 

스프링에서 인터셉터는 HandlerInterceptorAdapter를 상속받아 구현할 수 있습니다. 

해당 클래스는 preHandle, postHandle, afterCompletion, afterConcurrentHandlingStarted

### 인터셉터 메소드

preHandle-컨트롤러의 메서드에 매핑된 특정 URI를 호출했을 때
컨트롤러에 접근하기 전에 실행되는 메서드입니다.
우리는 사용자가 화면에서 어떠한 기능을 수행했을 때
해당 기능과 매핑된 URI의 정보를 쉽게 파악할 수 있도록
콘솔에 로그를 출력하도록 처리합니다.

postHandle-컨트롤러를 경유한 다음, 화면(View)으로 결과를 전달하기 전에 실행되는 메서드입니다.
우리는 요청의 끝을 알리는 로그를 콘솔에 출력하도록 처리합니다