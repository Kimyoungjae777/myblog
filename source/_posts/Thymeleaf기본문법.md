---
title: "Thymeleaf 자주 사용하는 문법"
author: "Young Jae Kim"
date: '2022-11-17'
output:
  html_document:
    keep_md: true
category: SpringBoot

---

![Untitled](images/Thymeleaf/1.png)
# Thymeleaf 자주 사용하는 문법

### th:text

- 화면에 값을 출력할 때 사용

```java
<span th:text="${nickname}"></span>
```

### th:object

- form submit을 할 때, form의 데이터가 th:object에 설정해준 객체로 받아진다.

### th:field

- 각각 필드들을 매핑을 해주는 역할을 한다. 설정해 준 값으로, th:obecjt에 설정해 준 객에의 내부와 매핑해준다.

```java
<form th:action="@{/sign-up}" th:object="${signUpForm}" method="post">
                <div class="form-group">
                    <label for="nickname">닉네임</label>
                    <input id="nickname" type="text" th:field="*{nickname}" class="form-control">
                </div>
            </form>
```

<form> 안의 데이터를 sign-up controller 로 보낼거고 , signUpForm 객체의 nickname으로 매핑시켜준다. 

### th:fragment

- header,footer,navigation bar 같이 모든 페이지에 보여져야하는 항목인 경우 따로 분리해서 관리한다.