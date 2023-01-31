---
title: "Select from world"
author: "Young Jae Kim"
date: '2023-1-30'
categories: 
- Development
- SqlZoo
tags:
- Development
- SQLZOO

---
# SELECT from World

### 1.[Read the notes about this table.](https://sqlzoo.net/wiki/Read_the_notes_about_this_table.)
 Observe the result of running this SQL command to show the name, continent and population of all countries.

<데이터를 관찰하라>

```sql
select name,continent,population
from world
```

![Untitled](images/selectFromWorld/0.png)

### 2. [How to use WHERE to filter records.](https://sqlzoo.net/wiki/WHERE_filters)
 Show the name for the countries that have a population of at least 200 million. 200 million is 200000000, there are eight zerosrds

인구가 최소 200millon  이상인 나라이름을 출력하라

```sql
SELECT name FROM world
WHERE population >= 200000000
```

![Untitled](images/selectFromWorld/1.png)

### 3.

Give the `name`
 and the **per capita GDP**
 for those countries with a `population`
 of at least 200 million.

인구가 200000000 이상인 나라 조건에서 , 인구별 1인당 gdp를 구하여라 

```sql
select name,GDP/population
from world 
where population>=200000000
```

![Untitled](images/selectFromWorld/2.png)

# 4.

Show the `name` and `population` in millions for the countries of the `continent` 'South America'. Divide the population by 1000000 to get population in millions.

‘South America’ 대륙의 이름과 인구를 100만으로 나눈것을 출력하라

```sql
select name,population/1000000
from world 
where continent='South America'
```

![Untitled](images/selectFromWorld/3.png)

# 5.

Show the `name` and `population` for France, Germany, Italy

‘France’,’Germany’,’Italy’ 이름을 가진 나라들의 이름과 인구를 출력하라.

```sql
select name,population 
from world
where name IN('France','Germany','Italy')
```

IN 연산자는  OR 역할을 한다.  NAME 에 괄호 안의 문자열이 들어간 NAME을 뽑아낸다. 

![Untitled](images/selectFromWorld/4.png)

# 6.

Show the countries which have a `name` that includes the word 'United'

‘United’ 문자열을 포함하는 나라의 이름을 출력하라

```sql
select name 
from world
where name like('%United%')
```

![Untitled](images/selectFromWorld/5.png)

# 7.

Two ways to be big: A country is **big** if it has an area of more than 3 million sq km or it has a population of more than 250 million.

**Show the countries that are big by area or big by population. Show name, population and area.**

위에서 언급한 대도시의 조건에 부합하는  name,population,area 를 출력하라

```sql
select name,population,area
from world 
where area>3000000 or population>250000000
```

- OR 연산자 사용 !!

![Untitled](images/selectFromWorld/6.png)

# 8.

**Exclusive OR (XOR). Show the countries that are big by area (more than 3 million) or big by population (more than 250 million) but not both. Show name, population and area.**

- Australia has a big area but a small population, it should be **included**.
- Indonesia has a big population but a small area, it should be **included**.
- China has a big population **and** big area, it should be **excluded**.
- United Kingdom has a small population and a small area, it should be **excluded**

XOR 문제 A 상황 과 B상황을 구하되 , A,B 둘다 일어나는 상황은 제외하라 

```sql
select name,population,area
from world 
where (area>3000000 or population>250000000) and  NOT (area>3000000 and population>250000000)
```

- 괄호를 묶어서  원래 대도시의 조건을 넣어준다. 그리고 AND 연산자로 BOTH 에 소하는 것들은 제외해준다.

![Untitled](images/selectFromWorld/7.png)

# 9.

Show the `name` and `population` in millions and the GDP in billions for the countries of the `continent` 'South America'. Use the [ROUND](https://sqlzoo.net/wiki/ROUND) function to show the values to two decimal places.

**For South America show population in millions and GDP in billions both to 2 decimal places.**

South America 의  100만명당 인구를 출력하라  그리고 gdp 를 2째자리 까지 반올림 하여라 .

```sql
select name,round(population/1000000,2),round(gdp/1000000000,2)
from world 
where continent='South America'
```

![Untitled](images/selectFromWorld/8.png)

### 10.

Show the `name` and per-capita GDP for those countries with a GDP of at least one trillion (1000000000000; that is 12 zeros). Round this value to the nearest 1000.

**Show per-capita GDP for the trillion dollar countries to the nearest $1000.**

- gdp가 최소 1000000000000  인 나라의 1인당 gdp를 3자리까지 반올림하여 표현하리

```sql
select name,round(gdp/population,-3) 
from world 
where gdp>=1000000000000
```

![Untitled](images/selectFromWorld/9.png)

### 

# 11.

Greece has capital Athens.

Each of the strings 'Greece', and 'Athens' has 6 characters.

**Show the name and capital where the name and the capital have the same number of characters.**

- You can use the [LENGTH](https://sqlzoo.net/wiki/LENGTH) function to find the number of characters in a string

For Microsoft SQL Server the function LENGTH is LEN

- (NAME 과 CAPITAL 의 숫자 길이가 같은 NAME 과 CAPITAL 을 출력하라)

```sql
SELECT name,capital
from world 
where LEN(name)=LEN(capital)
```

![Untitled](images/selectFromWorld/10.png)

# 12.

The capital of Sweden is Stockholm. Both words start with the letter 'S'.

**Show the name and the capital where the first letters of each match. Don't include countries where the name and the capital are the same word.**

- You can use the function [LEFT](https://sqlzoo.net/wiki/LEFT) to isolate the first character.
- You can use `<>` as the **NOT EQUALS** operator.
- (NAME 과 CAPITAL 의 왼쪽에서 첫번째 글자가 같은것을 출력하며, 이름과 수도가 같지 않은  것들을 출력하라)

```sql
SELECT NAME,CAPITAL 
FROM WORLD 
WHERE LEFT(NAME,1)=LEFT(CAPITAL,1) AND NOT(NAME=CAPITAL)
```

![Untitled](images/selectFromWorld/11.png)

# 13.

**Equatorial Guinea** and **Dominican Republic** have all of the vowels (a e i o u) in the name. They don't count because they have more than one word in the name.

**Find the country that has all the vowels and no spaces in its name.**

- You can use the phrase `name NOT LIKE '%a%'` to exclude characters from your results.
- The query shown misses countries like Bahamas and Belarus because they contain at least one 'a'
- (a,e,i,o,u 를 모두 포함하며, 띄어쓰기를 포함하지 않는 나라를 출력하라.)

```sql
SELECT NAME 
FROM WORLD
WHERE 
NAME LIKE('%a%') and
NAME LIKE('%i%') and
NAME LIKE('%e%') and
NAME LIKE('%o%') and
NAME LIKE('%u%') and
NAME NOT LIKE('% %')
```

![Untitled](images/selectFromWorld/12.png)