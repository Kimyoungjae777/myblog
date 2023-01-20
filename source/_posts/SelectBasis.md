---
title: "Select Basis"
author: "Young Jae Kim"
date: '2023-1-20'
categories: 
- Development
- SqlZoo
tags:
- Development
- SQLZOO

---

# SELECT BASIS

### 

# 1.

The example uses a WHERE clause to show the population of 'France'. Note that strings (pieces of text that are data) should be in 'single quotes';

**Modify it to show the population of Germany**

ANSWER
<span style='background-color:#fff5b1'>
SELECT population FROM world
WHERE name = 'Germany'
</span>
![Untitled](images/SelectBasis/0.png)

- Where 을 이용한 조건문 활용 .

# 2.

Checking a list The word **IN** allows us to check if an item is in a list. The example shows the name and population for the countries 'Brazil', 'Russia', 'India' and 'China'.

**Show the name and the population for 'Sweden', 'Norway' and 'Denmark'.**

ANSWER
<span style='background-color:#fff5b1'>
SELECT name, population FROM world
WHERE name IN ('Sweden', 'Norway', 'Denmark');
</span>

![Untitled](images/SelectBasis/1.png)

- IN 연산자를 통하여 조건문 형성
- IN 연산자→ OR 을 여러번 걸어주는 것과 동일 .
- name 에 스웨덴,노르웨이,덴마크 가 들어간 데이터에 한해서 name과 population 을 조회.

# 3.

Which countries are not too small and not too big? `BETWEEN` allows range checking (range specified is inclusive of boundary values). The example below shows countries with an area of 250,000-300,000 sq. km. Modify it to show the country and the area for countries with an area between 200,000 and 250,000.

Answer
<span style='background-color:#fff5b1'>
select name,area from world
where area between 200000 and 250000

</span>



![Untitled](images/SelectBasis/2.png)

- between 을 통해서 area의 데이터를 필터링 해준다 . 200,000 에서 250000 있는 값을 찾는 것.