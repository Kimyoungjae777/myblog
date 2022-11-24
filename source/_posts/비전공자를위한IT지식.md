---
title: "비전공자를 위한 it지식"
author: "Young Jae Kim"
date: '2021-001-06'
output:
  html_document:
    keep_md: true
categories:
- Book
---
# 비전공자를 위한 이해할 수 있는 IT 지식

![Untitled](images/itBook/0.png)

### 책에서 다루고자 하는 주제

- 운영체제 개발자에서 부터 프론트엔드 ~ 백엔드, git에 관련 설명 까지.

![Untitled](images/itBook/1.png)

### 1장:프로그래밍 언어와 운영체제

- 개발자가 프로그래밍 언어로 컴파일러에게 보내주면 컴파일러는 이를 기계어로 바꾸어 컴퓨터에게 알려준다.

![Untitled](images/itBook/2.png)

### IDE(Integrated Development Environment)

- 통합개발환경 ⇒ 개발자들의 개발을 편히도와주는 Tool

**고수준 언어**: 인간친화적 ⇒ 고수준언어는 인간친화적인 만큼 기계어와는 멀기 때문에 사양이 많이 필요하다

**저수준 언어:**  컴퓨터친화적 ⇒ 저수준언어는 컴퓨터친화적인 만큼 기계어와 가깝기 사양이 덜 필요하다

![Untitled](images/itBook/3.png)

### 컴퓨터 하드웨어

- **cpu**: 컴퓨터의 머리
- **HDD,SSD**:컴퓨터의 창고

프로그램을 실행한다 ⇒HDD,SSD에 있는 프로그램을 CPU에 전달한다.

**프로그램을 실행한다**⇒ 하드디스크의 3번 플레터에 접근해서, 포토샵 데이터를 2번 메모리의 3번 구역에 올린뒤 CPU에게 일을시키자 ⇒ 이러한 과정이 일어나는데 이러한 과정을 ***운영체제***가 해주는 것이다.

### 2장.네트워크 , 클라이언트,서버

- LAN(Local Area Network)컴퓨터가 연결된 작은지역
- MAN(MetroPolitan Area Network):도시의 여러LAN을 하나로 연결
- WAN(Wide Area Network):나라와 나라를 연결

![Untitled](images/itBook/4.png)

- **IP**:컴퓨터의 주소로써 컴퓨터가 늘어날수록 IP 많이 필요

### 플레이 스토어에서  카카오톡을 다운받으면 생기는 일

![Untitled](images/itBook/5.png)

- 여기서 나의 스마트폰은 클라이언트가 되는것 이고, 애플이 켜놓은 컴퓨터는 서버가 되는것 이다.

### 도대체 우분투가 뭐죠?

- 우분투는 리눅스(운영체제)의 한 버젼으로, 리눅스는 무료이기 때문에 리눅스 초기버젼을 발전시켜 새롭게 나온 버젼이고 사람들이 제일 많이 쓰는 버젼이다

### 3장 API와 JSON

### POST는 뭐고 GET은 뭐죠?

API = 서버는 요청에 따라 적합한 처리를 해서 응답을 준다. 하지만 컴퓨터는 한글을 모릅니다. 어떤 요청이 ‘메세지를 달라’는 요청인지, ‘로그인 시켜줘’ 라는 요청인지 알 수 없습니다. 요청을 구분할 수 있도록 하는 ‘**체계**’가 API이다

API는 클라이언트,서버와 같은 서로 다른 프로그램에서 요청과 응답을 주고 받을 수 있게 만든 체계입니다. 

![Untitled](images/itBook/6.png)

![Untitled](images/itBook/7.png)

![Untitled](images/itBook/8.png)

![Untitled](images/itBook/9.png)

- API에는 형식이 있는데 가장 많이쓰는 형식이 JSON이다.

### API 문서 읽는 방법

![Untitled](images/itBook/10.png)

- **API제목** : GET_CAKES →케이크를 달라는 API에 관해서 설명하는 문서.
- 파란색 GET: 클라이언트에서 서버로 요청을 보낼때,GET 요청으로 보내는 것이다 ⇒ READ(조회) 의미
- **API주소:** 컴퓨터의 위치
- **REQUEST,RESPONE :** REQUEST 일때랑 RESPONSE 일때랑 문서를 나누어 놓은것
- **PARAMETER :** 요청을 보낼때 필요한 변수

![Untitled](images/itBook/11.png)

<RESPONSE> 부문

- 200번대 요청이 성공하였을때
- 400번대 500번대 요청이 실패하였을때

### 프레임워크와 라이브러리

### 프레임워크

- 원하는 기능 구현에 집중하여 개발할 수 있도록 일정한 형태와 필요한 기능을 갖추고 있는 골격,뼈대를 의미 한다.
- 애플리케이션 개발 시 필수적인 코드, 알고리즘,DB 연동과 같은 기능들을 위해 어느정도 뼈대를 제공 하며 이러한 뼈대 위에서 사용자는 코드를 작성하여 애플리케이션을 개발한다. 앱/서버 등의 구동, 메모리관리,이벤트 루프 등의 공통된 부분은 프레임워크가 관리하며, 사용자는 프레임워크가 정해준 방식대로 클래스,케서드를 구현하면 된다.

**EX)**

- Java 서버 개발에 사용되는 Spring
- Python 서버 개발에 사용되는 Django, Flask
- 안드로이드 앱 개발에 사용되는 Android
- 아이폰 앱 개발에 사용되는 Cocoa Touch
- 웹 개발에 사용되는 Angular, Vue.js 등
- 자바 기반의 JSP를 위한 프레임 워크 Struts
- 루비로 작성된 MVC패턴을 이용하는 Ruby on Rails

### 라이브러리

- 소프트웨어를 개발할 때 컴퓨터 프로그램이 사용하는 비휘발성 자원의 모임. 즉 특정 기능을 모와둔 코드, 함수들의 집합이며 코드 작성 시 활용 가능한 도구들을 의미합니다.

**EX)**

- Python pip로 설치한 패키지/모듈 (tensorflow, pandas, beautifulsoup 등등)
- C++의 표준 템플릿 라이브러리 (STL)
- Node.js에서 npm으로 설치한 모듈
- HTML의 클라이언트 사이드 조작을 단순화하는 JQuery
- 웹에서 사용자 인터페이스 개발에 사용되는 React.js