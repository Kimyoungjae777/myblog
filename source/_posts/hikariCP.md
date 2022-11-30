---
title: "Hikari CP란?"
author: "Young Jae Kim"
date: '2022-12-01'
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
# Hikari CP

- HikariCP는 Database와의 커넥션 풀을 관리한다. 관리해주어야하는 이유는 JDBC커넥션을 맺는 과정은 상당히 복잡하고 자원을 많이 소모하는 작업이기 때문에 관리를 해야 성능적으로 좋기 때문이다. 만약 요청이 들어올 때 Thread가 Database와의 커넥션을 맺는다면 데이터베이스 뿐만 아니라 앱서버 입장에서도 굉장히 부하가 심하게 발생 할 것이다. 그런데 HikariCP는 미리 정해놓은 만큼에 커넥션은 pool에 담아 놓는다. 요청이 들어오면 Thread가 커넥션을 요청하고, Hikari는 Pool내에 있는 커넥션을 연결해준다.

⇒ 결론: 자바와 데이터베이스를 연결시키는 일은 부하가 많이되는 작업이기 때문에 ,  미리정해놓은 커넥션을 Pool에 담아 놓고 요청이 들어오면 Thread가 커넥션을 요청하고, Hikari pool 내에 있는 커넥션을 연결해준다.

# Connection Pool (커넥션 풀)

- 데이터 연동과정에서 일반적인 연동과정은 웹 어플리케이션이 필요할 때마다 데이터베이스에 연결하여 작업하는 방식이다. 그런데 이런 식으로 필요할 때마다 연동해서 작업할 경우 데이터베이스 연결에 시간이 많이 걸린다는 문제가 있다. 이 문제를 해결하기 위해 현재는 웹 어플리케이션이 실행됨과 동시에 연동할 데이터베이스와의 연결을 미리 설정해 두고, 필요할 때마다 미리 연결해 놓은 상태를 이용해 빠르게 데이터베이스와 연동하여 작업을 한다. 이 작업을 Connection Pool 이라고 한다.

![Untitled](images/hikari/0.png)

출처:[Hikari Connection Pool이란? (tistory.com)](https://masssal.tistory.com/16)