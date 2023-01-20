---
title: "Select name"
author: "Young Jae Kim"
date: '2023-1-21'
categories: 
- Development
- SqlZoo
tags:
- Development
- SQLZOO

---

# SELECT NAME

# 1.

You can use `WHERE name LIKE 'B%'` to find the countries that start with "B".

- The % is a *wild-card* it can match any characters

**Find the country that start with Y (Y 로 시작하는 나라의 이름을 출력하라.)**

```sql
select name 
from world
WHERE name like 'Y%' 
```

![Untitled](images/SelectName/0.png)

# 2.

**Find the countries that end with y (Y로 끝나는 나라의 이름을 출력하라)**

```sql
SELECT name from world
where name like '%y'
```

![Untitled](images/SelectName/1.png)

# 3.

Luxembourg has an **x** - so does one other country. List them both.

**Find the countries that contain the letter x**

(x 라는 문자를 포함하는 나라를 출력해라)

```sql
select name from world
where name '%x%'

```

# 4.

Iceland, Switzerland end with **land** - but are there others?

**Find the countries that end with land**

(마지막 글자가 land로 끝나는 나라를 출력하라)

```sql
select name
from world 
where name like '%land'
```

![Untitled](images/SelectName/2.png)

# 5.

Columbia starts with a **C** and ends with **ia** - there are two more like this.

**Find the countries that start with C and end with ia**

(C로 시작해서 -ia 로 끝나는 나라를 출력하라)

```sql
select name 
from world
where name like 'C%ia'

```

![Untitled](images/SelectName/3.png)

# 6.

Greece has a double **e** - who has a double **o**?

**Find the country that has oo in the name**

(oo 를 가지는 나라를 출력하라)

```sql
select name 
from world 
where name like '%oo%'

```

![Untitled](images/SelectName/4.png)

# 7.

Bahamas has three **a** - who else?

**Find the countries that have three or more a in the name**

(a 를 3 개나 3개이상 가진 나라를 출력하라)

```sql
select name from world 
where name like '%a%a%a%'
```

![Untitled](images/SelectName/5.png)

# 8.

India and Angola have an **n** as the second character. You can use the underscore as a single character wildcard.

**`SELECT** name **FROM** world
 **WHERE** name **LIKE** '_n%'
**ORDER** **BY** name`

**Find the countries that have "t" as the second character.**

(t 가 두번째 글자에 들어가는 나라를 찾아라)

```sql
select name from world 
where name like '_t%'
```

![Untitled](images/SelectName/6.png)

# 9.

Les**o**th**o** and M**o**ld**o**va both have two o characters separated by two other characters.

**Find the countries that have two "o" characters separated by two others.**

```sql
select name 
from world 
where name like '%o__o%'
```

![Untitled](images/SelectName/7.png)

# 10.

Cuba and Togo have four characters names.

**Find the countries that have exactly four characters.**

```sql
select name from world
where name like '____'
```

![Untitled](images/SelectName/8.png)

# 11.

The capital of **Luxembourg** is **Luxembourg**. Show all the countries where the capital is the same as the name of the country

**Find the country where the name is the capital city.**

```sql
select name 
from world
where name=capital
```

![Untitled](images/SelectName/9.png)

# 12.

The capital of **Mexico** is **Mexico City**. Show all the countries where the capital has the country together with the word "City".

**Find the country where the capital is the country plus "City".**

(capital 이 name +city 인  나라를 출력하라)

```sql
select name 
from world 
where capital like concat(name,' city')
```

![Untitled](images/SelectName/10.png)

# 13.

**Find the capital and the name where the capital includes the name of the country.**

(capital 과 name 을출력하는데 , 캐피탈이 나라의 이름을 포함하는 애들을)

 

```sql
select capital,name
from world
where capital like '%'+name+'%'
```

# 14.

**Find the capital and the name where the capital is an extension of name of the country.**

You *should* include **Mexico City** as it is longer than **Mexico**. You *should not* include **Luxembourg** as the capital is the same as the country.

(캐피탈과 이름을 출력하는데, 캐피탈이 이름의 연장인 ) 그러나 룩셈부르크 처럼 name과 capital 이 같은 name 은 제외

```sql
select capital,name
from world
where capital like concat(name,'_%')

====

select capital,name 
from world
where capital like name+'_%'

```

![Untitled](images/SelectName/11.png)

# 15.

For **Monaco-Ville** the name is **Monaco** and the extension is **-Ville**.

**Show the name and the extension where the capital is an extension of name of the country.**

capital 에 country name 이 들어가고 추가로 연장문이 들어간 것 들을 name 과 ext 로 나누어서 출력하라 ext 는 연장된것만!!

```sql
select name,replace(capital,name,'') as ext
from world
where capital like concat(name,'_%')
```

![Untitled](images/SelectName/12.png)