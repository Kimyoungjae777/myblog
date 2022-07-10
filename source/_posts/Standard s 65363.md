---
title: "정규화 StandardScaler"
author: "Young Jae Kim"
date: '2022-03-15'
output:
  html_document:
    keep_md: true
category: -전처리

---

images/make_blog
# Standard scaler() 정규화

- 모든 Feature 들이 스케일(범위) 가 같은 것 은 아니기 때문에 전처리 할때는 , 스케일들을 정규화 시켜주는 것이 필요하다. → 정규화를 시켜주어야 스케일링이 적용되며 서로 스케일이 다름으로써 나오는 오류를 없애줄 수 있는 것이다.

- 원핫 인코딩 되어 있는 데이터나, 숫자에 통계학적 의미가 없는 데이터들은  스케일링 해줄 필요 없다

- 스케일링은 각 컬럼별로 해주는 것이 좋다, 다 같이 해주면 평균이나 이러한 것들이 엉켜서 버그를 일으킬 수 있기 때문이다.

![Untitled](images/make_blog/b.png)

```python
import pandas as pd
from pandas import DataFrame as df
import numpy as np
from sklearn.preprocessing import StandardScaler

df1=df(data={'height':[170,160,180,170,175,180,160,165,186,172],
       'weight':[65,55,70,60,62,72,60,58,100,67],
       'favor':[1,0,1,0,0,1,1,1,0,1]})

df1.head()
# 스케일링 해줄때 각 컬럼별 array 로 변환해 주어야 하기 때문에
height_df=df1['height']
weight_df=df1['weight']
favor_df=df1['favor']

height_df=np.array(height_df).reshape(-1,1)
weight_df=np.array(weight_df).reshape(-1,1)
favor_df=np.array(favor_df).reshape(-1,1)
```

![Untitled](images/make_blog/a.png)

```python
scaling_height=StandardScaler().fit_transform(height_df)
scaling_weight=StandardScaler().fit_transform(weight_df)
scaling_height  # 스케일링 된 것을 볼 수 있다
```

![Untitled](images/make_blog/c.png)