---
title: "SqlReplace함수"
author: "Young Jae Kim"
date: '2022-01-31'
output:
  html_document:
    keep_md: true
categories: 
- Development
- DataBase
tags:
- Development
- DataBase

---

# SQL REPLACE 함수

### 특정문자 치환

```sql
SELECT replace('oracle database','oracle','ora') AS reuslt1
, replace('oracle database','database','data') AS result2
```

![Untitled](images/sqlReplace/0.png)

### 함수사용법

**Replace(”칼럼명 or 문자열”,”찾을문자”,”치환문자”)**

### 다중 문자열 치환(중첩 Replace)

```sql
SELECT REPLACE(REPLACE('oracle database','oracle','ora'),'database','data')
FROM dual;
```

![Untitled](images/sqlReplace/1.png)

### 특정문자 제거

```sql
SELECT REPLACE('Oracle Database','cle') as result1
SELECT REPLACE('Oracle Database','Database') as result2
SELECT REPLACE('Oracle Database','Database','')as result3
from dual;

```

![Untitled](images/sqlReplace/2.png)

- Replace 함수를 사용하여 특정 문자를 제거할 때는 “치환문자”항목은 생략하고”찾을문자”

       만 입력하면 된다