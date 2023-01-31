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
# SQL Round 함수

- 오라클 sql 에서 소수점 자리수를 지정하기 위해서 ROUND 함수를 사용한다. ROUND 함수는 특정 소수점을 반올림하고 나머지를 버리는 함수 이다 .

- 소수점을 반올림하지 않고 절사만 원한다면 TRUNC 함수를 사용해야 한다.

### ROUND 함수

- 함수: ROUND(”값”,”자리수”)

### 소수점 반올림 -1 (소수점 첫째자리)

```sql
SELECT ROUND(1235.543)    --①
     , ROUND(1235.443)    --②
     , ROUND(1235.443, 0) --③
  FROM dual
```

![Untitled](images/sqlRound/0.png)

- 1,2,3 모두 소수점 첫번째 자리수를 반올림 한다.  즉 0번째 자리까지 나타낸다고 생가하면 된다 .

### 소수점 반올림 -2 (소수점 둘째자리)

```sql
SELECT ROUND(1235.345, 1) --①
     , ROUND(1235.345, 2) --②
     , ROUND(1235.345, 3) --③
  FROM dual
```

![Untitled](images/sqlRound/1.png)

- 결론적으로 , 자릿수는 몇번째 자리까지 표시하고 반올림 하냐  이것이 중요하다 .

### 정수 반올림

```sql
SELECT ROUND(1235.345, -1) --①
     , ROUND(1235.345, -2) --②
     , ROUND(1235.345, -3) --③
  FROM dual
```

![Untitled](images/sqlRound/2.png)

- ROUND 함수는 소수점 뿐만아니라 정수도 반올림이 가능하다,
- 그런데 정수 반올림에서는 나타내어진 자릿수에서 반올림을 실행한다.

###