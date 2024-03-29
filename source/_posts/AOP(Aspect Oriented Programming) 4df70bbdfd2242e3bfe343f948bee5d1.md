
---
title: "AOP "
author: "Young Jae Kim"
date: '2022-08-06'
categories: 
- Development
- 기본개념
tags:
- Development
- 기본개념
---
# AOP(Aspect Oriented Programming)

### REFERENCE:[스프링 부트(Spring Boot) - AOP와 트랜잭션(Transaction) 설정하기 [개발을 시작해봐요!] (tistory.com)](https://congsong.tistory.com/25?category=749196)

AOP는 관점 지향 프로그래밍입니다. 

AOP는 자바와 같은 객체 지향 프로그래밍을(OOP)을 더욱 OOP 답게 사용할 수 있도록 도와주는 역할을 합니다.

AOP는 여러 개의 핵심 비즈니스 로직 외에 공통적으로 처리되어야 하는 로그출력,보안처리,예외처리와 같은 코드를 별도로 분리해서 하나의 단위로 묶는 모듈화의 개념으로 생각할 수 있습니다. 

하나의 단위로 묶는 모듈화의 개념으로 생각할 수 있습니다

AOP에서 관점에서 관점은 핵심적인 관점과 부가적인 관점으로 나눌수 있습니다.

핵심적인 관점은 핵심 비즈니스 로직을 의미하고, 부가적인 관점은 앞에서 이야기한 공통으로 처리되어야 하는 코드를 의미합니다.

![Untitled](images/AOP/Untitled.png)

각각의 화살표는 하나의 기능을 구현하는데 필요한 작업을 의미. 

MVC 패턴의 특성상, 컨트롤러 ⇒ 서비스 ⇒DAO(Mapper) tnsdmfh wkrehdgkqslek. 

필수적으로 처리되어야 하는 로그,보안,트랜잭션,예와처리와 같은 부가적인 기능들이 정말 규모가 커다란 시스템에서 각각의 기능에 추가된다면 코드가 엄청나게 길어진다. 

AOP는 이러한 문제를 관점이라는 개념을 통해 해결할 수 있습니다

앞에서 이야기 했던 부가적인 관점에서는

핵심 비즈니스 로직이 어떤 기능을 수행하는지에 대해 전혀 알 필요가 없습니다. 

단지, 핵심 비즈니스 로직 안에서 필요한 시점에 부가적인 관점이 포함되기만 하면 된다.

![Untitled](images/AOP/2.png)

객체 지향 프로그래밍과 달리, 부가적인 관점이 핵심 비즈니스 로직의 바깥에 포함되어 있다.

AOP를 적용하면 로그,보안,트랜잭션,예외처리와 같은 부가적인 기능들을 일일이 추가하지 않아도 된다. 

[어노테이션에 대한 표](https://www.notion.so/53d5fc9fc5f2475faa176238b6a45814)

[어노테이션에 대한 표](https://www.notion.so/3e2ecdc21f60445ea1929fc76ed9dd84)