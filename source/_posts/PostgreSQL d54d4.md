---
title: "postgresql_설치"
author: "Young Jae Kim"
date: '2022-03-23'
category: Postgresql
--- 
images/postgresql/

# PostgreSQL 설치

- WSL2 에서 PostgreSQL 을 설치.
- pgAdmin은 windows에 설치한다.

### 터미널 업그레이드

- 먼저 WSL 터미널을 열고, 패키지를 모두 업그레이드 및 업그레이들 해준다

![Untitled](images/postgresql/Untitled.png)

![Untitled](images/postgresql/Untitled%201.png)

- 이번에는 wsl2에서(ubuntu 및 다른것을 사용해도 가능.) PostgreSQL 을 설치한다 . 설치하고 버전을 확인해준다.

![Untitled](images/postgresql/Untitled%202.png)

- 포트가 활성화 되어 있는지 확인하여준다 포트가 활성화 되어 있지 않다면 , 아래와 같이 표시될 것이다.

![Untitled](images/postgresql/Untitled%203.png)

- 이번에는 포트를 활성화 시켜준다.

![Untitled](images/postgresql/Untitled%204.png)

### 사용자 계정 Password 설정

![Untitled](images/postgresql/Untitled%205.png)

## pgAdmin 설치

- **[https://www.pgadmin.org/download/pgadmin-4-windows/](https://www.pgadmin.org/download/pgadmin-4-windows/)**

![Untitled](images/postgresql/Untitled%206.png)

![Untitled](images/postgresql/Untitled%207.png)

![Untitled](images/postgresql/Untitled%208.png)

- 이번에는 서버를 설정하도록 한다.

![Untitled](images/postgresql/Untitled%209.png)

![Untitled](images/postgresql/Untitled%2010.png)

- connection tab에는 아래와 같이 입력한다.
- password는 wsl2에서 입력했던 password를 입력한다.

![Untitled](images/postgresql/Untitled%2011.png)

- 이런 에러가 나온다면 아래와 같은 코드를 작성하여 준다.
- 아래 코드 설정시 service가 활성화 되어 있어야 한다.

`$ sudo -u postgres psql -c "ALTER USER postgres PASSWORD '<new-password>';"`

`$ sudo -u postgres psql -c "ALTER USER postgres PASSWORD '<new-password>';"`

- 위 설정이 끝난 후, 재접속하면 정상적으로 접근이 되는 것을 확인할 수 있다.

![Untitled](images/postgresql/Untitled%2012.png)

## DB 생성 및 확인

- test 서버에 접속을 하고, DB를생성 한다.

![Untitled](images/postgresql/Untitled%2013.png)

- 새로운 데이터베이스인 dataenengineering 로 명명한다

![Untitled](images/postgresql/Untitled%2014.png)

- 이번에는 아래 그림과 같이 dataenengineering 데이터베이스의 노드 중 shemas를 확장하고 다시 public을 확장한다.
- Table 에서 마우스 우 클릭후 create-Table을 순차적으로 선택한다.

![Untitled](images/postgresql/Untitled%2015.png)

- General 탭에서 users 라고 명명한다.

![Untitled](images/postgresql/Untitled%2016.png)

- column 탭에서는 아래와 같이 테이블 열을 추가한다.

![Untitled](images/postgresql/Untitled%2017.png)

- 이번에는 psql에 접속후 dataenengineering DB와 생성된 테이블을 조회하는 쿼리를 실행한다.

- dataenengineering 테이블이 조회되는지 확인한다

![Untitled](images/postgresql/Untitled%2018.png)

- 이번에는 dataenengineering DB에 연결후 테이블을 조회하도록 한다

![Untitled](images/postgresql/Untitled%2019.png)