---
title: "loc 와 iloc 의 차이 "
author: "Young Jae Kim"
date: '2022-03-16'
category: Pandas
---



# loc 와 iloc 의 차이

- loc:label 을 통해서 값 찾는다

- iloc:integer position 을 통해 값을 찾는다

문법 공통점:df.loc[[행],[열]]

- loc 의 경우

```python
df1.loc[:,2,['Survived', 'Pclass','Name']]

```

![Untitled](/images/make_blog/iloc.png)

- iloc 의 경우

```python
df1.iloc[:2,1:4]
```

![Untitled](/images/make_blog/loc.png)