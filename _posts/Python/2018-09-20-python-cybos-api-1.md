---
layout: post
title: Python with Cybos API
category: Python
tags: [Python, Cybos]
published: true
comments: false
---

## Stock Prediction
- Stoack Prediction을 위한 과거의 코드를 정리하고자 한다.
- 데이터는 대신증권API,  NaverFinance + SejongData에서 웹크롤링 / 툴은 R + Python + MySQL을 활용하였다.
- Stock Prediction이라고 거창한 이름을 붙였으나, 여전히 나에게는 숙제인 분야이다.
- 대신증권API는 Windows에서만 가능하다.

```python
#-*-coding:utf-8-*-     # 파일 인코딩 정의
import win32com.client  # Windows Resource에 접근하기 위한 모듈
import pandas as pd     # pandas
import numpy as np      # numpy
import pymysql          # python mysql 연결 모듈

#====== code =======#
#                                   #
#===================#
```

해당 모듈을 import 한다.


```console
jupyter nbconvert --to markdown <xxxxx.ipynb>
```

*.ipynb 파일을 markdown 파일로 변경한다.
