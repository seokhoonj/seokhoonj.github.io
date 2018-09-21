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
- 데이터는 대신증권 Cybos API에서 다운로드,  NaverFinance + SejongData에서 크롤링을 하였다.
- 개발툴은 R + Python + MySQL을 활용하였다.
- 참고로, 대신증권 Cybos API는 Windows에서만 가능하다.
- Stock Prediction이라고 거창한 이름을 붙였으나, 여전히 나에게는 숙제인 분야이다.  

1. stockList를 Pandas Dataframe으로 만들기


```python
#-*-coding:utf-8-*-           # 파일 인코딩 정의
import win32com.client  # Windows Resource에 접근하기 위한 모듈
import pandas as pd      # pandas
import numpy as np       # numpy
import pymysql              # python mysql 연결 모듈
import os.path

# CpCodeMgr 불러오기
CpCodeMgr = win32com.client.Dispatch('CpUtil.CpCodeMgr')
CpStockCode = win32com.client.Dispatch('CpUtil.CpStockCode')

# 장시작 마감 시간 (별 의미는 없음)
CpCodeMgr.GetMarketStartTime()
CpCodeMgr.GetMarketEndTime()

# kospi, kosdaq code
kospiCode = list(CpCodeMgr.GetStockListByMarket(1))
kosdaqCode = list(CpCodeMgr.GetStockListByMarket(2))

kospiList = pd.DataFrame({'groupcode': '001', 'groupname': '종합주가지수', 'code': list(kospiCode), 'name': np.arange(len(kospiCode)), 'fullcode': np.arange(len(kospiCode))},
                         columns=['groupcode', 'groupname', 'code', 'name', 'fullcode'])
kosdaqList = pd.DataFrame({'groupcode': '201', 'groupname': '(코스닥)종합', 'code': list(kosdaqCode), 'name': np.arange(len(kosdaqCode)), 'fullcode': np.arange(len(kosdaqCode))},
                         columns=['groupcode', 'groupname', 'code', 'name', 'fullcode'])

# concat kospi / kosdaq                       
stockList = pd.concat([kospiList, kosdaqList], ignore_index=True)
for i in range(len(stockList)):
        stockList.loc[i, 'name'] = CpCodeMgr.CodeToName(stockList.loc[i, 'code'])
        stockList.loc[i, 'fullcode'] = CpStockCode.CodeToFullCode(stockList.loc[i, 'code'])
        stockList.loc[i, 'control'] = str(CpCodeMgr.GetStockControlKind(stockList.loc[i, 'code']))
        stockList.loc[i, 'supervision'] = str(CpCodeMgr.GetStockSupervisionKind(stockList.loc[i, 'code']))
        stockList.loc[i, 'stts'] = str(CpCodeMgr.GetStockStatusKind(stockList.loc[i, 'code']))
        stockList.loc[i, 'capital'] = str(CpCodeMgr.GetStockCapital(stockList.loc[i, 'code']))
        stockList.loc[i, 'fismm'] = str(CpCodeMgr.GetStockFiscalMonth(stockList.loc[i, 'code']))
        stockList.loc[i, 'parent'] = str(CpCodeMgr.GetStockGroupCode(stockList.loc[i, 'code']))
        stockList.loc[i, 'kospi200'] = str(CpCodeMgr.GetStockKospi200Kind(stockList.loc[i, 'code']))
        stockList.loc[i, 'section'] = str(CpCodeMgr.GetStockSectionKind(stockList.loc[i, 'code']))
        stockList.loc[i, 'ex'] = str(CpCodeMgr.GetStockLacKind(stockList.loc[i, 'code']))
        stockList.loc[i, 'ldate'] = str(CpCodeMgr.GetStockListedDate(stockList.loc[i, 'code']))
        stockList.loc[i, 'closep'] = str(CpCodeMgr.GetStockYdClosePrice(stockList.loc[i, 'code']))

```

2. 만들어진 stockList를 미리 구성해 놓은 MySQL의 stockList 테이블에 INSERT 한다.


```python
conn = pymysql.connect(host='192.168.219.100', port=3306, user='root', passwd='45tp30djr!', db='test', use_unicode=True, charset='utf8', autocommit=True)
cur = conn.cursor()
cur.execute("DELETE FROM stockList")

print(os.path.basename(__file__), "(writing to db)")

for i in range(len(stockList)):
        cur.execute("INSERT INTO stockList (groupcode, groupname, code, name, fullcode, control, supervision, stts, capital, fismm, parent, kospi200, section, ex, ldate, closep) VALUES     ('"
                    + stockList.loc[i,'groupcode'] + "', '"
                                + stockList.loc[i,'groupname'] + "', '"
                                + stockList.loc[i,'code'] + "', '"
                                + stockList.loc[i,'name'] + "', '"
                                + stockList.loc[i,'fullcode'] + "', '"
                                + stockList.loc[i,'control'] + "', '"
                                + stockList.loc[i,'supervision'] + "', '"
                                + stockList.loc[i,'stts'] + "', '"
                                + stockList.loc[i,'capital'] + "', '"
                                + stockList.loc[i,'fismm'] + "', '"
                                + stockList.loc[i,'parent'] + "', '"
                                + stockList.loc[i,'kospi200'] + "', '"
                                + stockList.loc[i,'section'] + "', '"
                                + stockList.loc[i,'ex'] + "', '"
                                + stockList.loc[i,'ldate'] + "', '"
                                + stockList.loc[i,'closep'] + "');")

cur.close()
conn.close()

print(os.path.basename(__file__), "(wrote to db)")                                                         
```
