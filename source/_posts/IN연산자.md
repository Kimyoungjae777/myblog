---
title: "IN연산자"
author: "Young Jae Kim"
date: '2022-08-06'
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

# SQL IN 연산자

- SQL IN 구문은 WHERE절 뒤에 붙어서 칼럼이 특정값을 가지고 있는지 확인하는 용도로 쓰입니다.

### 사용법

```sql
SELECT 칼럼명 FROM 테이블명 WHERE 컬럼명 IN(값1,값2)
## 칼럼의 값이 값1 또는 값2에 해당하는 값만 출력
SELECT 칼럼명 FORM 테이블명 WHERE 칼럼명 NOT IN(값1,값2)
## 칼럼의 값이 값1,값2 어디에도 해당하지 않는 것만 출력
SELECT * FROM member WHERE name IN('제갈량','강감찬)
```

- name 칼럼에 제갈량 또는 강감찬 값을 가진 데이터만 출력이 되어서 제갈량과 강감찬 row 만 출력이 됩니다.