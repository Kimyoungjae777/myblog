---
title: "Spring과SpringBoot의 차이"
author: "Young Jae Kim"
date: '2022-03-19'
category: SpringBoot

---

# Spring 과 SpringBoot의 차이

### 스프링(spring)이란?

- 정확한 표현으로는 ‘스프링 프레임워크’
- 스프링 프레임워크는 자바에서 가장 많이 사용되는 프레임워크
- 의존성 주입과(DI) 제어역전(IOC), 관점 지향 프로그래밍(AOP) 이 가장 중요한 요소. 위 요소들을 통해 느슨한 결합을 달성할 수 있음. 위와 같이 느슨한 결합으로 개발한 어플리케이션은 단위테스트를 수행하기 용이함.

### 의존성 주입(DI,Dependency injection)

- 예제 코드와 같이 DI를 사용하지 않은 코드의 경우 Controller는 MyService 객체에 의존하게 됨
- 예제 코드 처럼 객체의 인스턴스를 얻게 되면 객체간의 결합도가 올라감.
- 예제 코드 처럼 객체의 인스턴스를 얻게 되면 객체간의 결합도가 올라감.
- 이런 코드 작성은 단위테스트를 위해 Mock 객체를 사용할 수 없게 됨

![Untitled](images/SpringVS_SpringBoot/0.png)

### 의존성 주입을 사용한경우

                                                                                  

![Untitled](images/SpringVS_SpringBoot/1.png)

- 예제 코드와 같이 DI를 사용하는 코드의 경우
- @Service, @Autowired 어노테이션을 통해 MyService의 인스턴스를 획득
- 위와 같이 코드를 작성하면 단위테스트 상황에서 Service 객체를 Mock 객체로 대체하여 쉽게 테스트 할 수 있음.
- 인스턴스를 직접 호출하는게 아니라 스프링 컨테이너에 있는 서비스 객체를 주입 받는 형태이기 때문에 진짜 Myservice에 인스턴스를 생성해주는게 아니라,MOCK 객체를 따로 만들어 주어서 Myservice 라는 객체 대신에 mock 객체를 넣어줄수 있다는 장점
- 이렇게되면 controller 를 테스트 할때 myservice 라는 객체는 테스트를 해주지 않아도 된다. (mock 객체로 대체 시키면 controller만 직접 테스트를 할 수 있다.)

### AOP

- 스프링 프레임워크에서 제공하는 강력한 기능 중 하나
- AOP는 쉽게 말해, OOP를 보완하는 수단으로, 여러 곳에 쓰이는 공통 기능을 모듈화하여 필요한 곳에 연결함으로써 유지보수 또는 재사용에 용이하도록 하는 것을 의미
- AOP를 통해 기존 프로젝트에 다양한 기능을 로직 수정 없이 추가할 수 있음.
- 이런 개발 방식을 통해 결합도를 낮춘 개발이 가능함.

### 스프링 프레임워크의 대표적 모듈

- Spring JDBC
- Spring MVC
- Spirng AOP
- Spring ORM
- Spring Test
- Spring Expression Language

### 스프링 부트가 나오게 된 이유

- 스프링 부트는 단지 실행만 하면 되는 스프링 기반의 어플리케이션을 쉽게 만들 수 있다.
- 스프링은 다양한 기능을 제공하고 있지만 그 기능을 사용하기 위한 설정에 많은 시간이 걸린다.

 

![Untitled](images/SpringVS_SpringBoot/2.png)

## 스프링 부트가 제공하는 기능

- 스프링 부트는 자동설정을 이용

-어플리케이션 개발에 필요한 모든 디펜던시를 프레임워크에서 관리

-jar파일이 클래스 패스에 있는경우 스프링 부트는 Dispatcher Servlet 으로 자동 구성됨 

-스프링 부트는 미리 설정되어 있는 Starter 프로젝트를 제공

-xml설정 없이 자바 코드를 통해 설정할 수 있음 

- 어플리케이션을 개발하면서 사용되는 디펜던시들은 호환되는 버전으로 관리 해줘야함

-이런 복잡도를 줄이기 위해 스프링 부트는 SpringBoot-Starter를 제공하여 자동으로 호환되는 버전을 관리 

### 모니터링 관리를 위한 스프링 액추에이더 제공

-서비스가 정상적으로 동작하는지 상태 모니터링 기능 제공

-스프링 액추에이터는 스프링 부트에서 제공하는 상태 정보를 보다 쉽게 모니터링할 수 있게 기능을 제공

### 스프링 부트 프로젝트의 의존성 관리

-spring boot starter dependency를 통해 다양한 패키지를 수용하고 있음.

-이를 통해 개발자는 dependency 관리(호환성 체크 등)에 대해 고려할 필요가 없어짐.

### 스프링 부트 프로젝트의 starter 디펜던시

![Untitled](images/SpringVS_SpringBoot/3.png)