---
title: "Sql_LENGTH함수"
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
# SQL LENGTH 함수

- 문자열을 출력하는 함수 .(**정확히는 BYTE길이를 가져오는 것**)

| NAME | NAME_KOREAN |
| --- | --- |
| CHEOL SU | 철수 |
| JEONG HUN | 정훈 |

```sql
SELECT LENGTH(NAME),LENGTH,NAME(NAME_KOREAN)
```

| LENGTH(NAME) | LENGTH,NAME(NAME_KOREAN) |
| --- | --- |
| 8 | 6 |
| 9 | 6 |
- NAME의 길이는 띄어쓰기를 포함하여 글자수에 +1 한 만큼 나오고
- 한국이름은 바이트로 표현되기때문에 6 이 나온다

### CHAR_LENGTH()

```sql
SELECT CHAR_LENGTH(NAME),CHAR_LENGTH(NAME_KOREAN)
FROM TABLE
```

| CHAR_LENGTH(NAME) | CHAR_LENGTH(NAME_KOREAN) |
| --- | --- |
| 8 | 2 |
| 9 | 2 |
- 문자 개수를 출력해준다 띄어쓰기도 문자이기 때문에 띄어쓰기는 포함되지만 한국이름은 2글자로 출력이 된다.