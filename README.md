# sales-prediction

[Dacon Mission 9](https://dacon.io/cpt9) 펀다 상점 매출 예측 경진대회, 2019.7.11 ~ 2019.8.30



### fbprophet
- facebook prophet
- negative data 제거
- sampling
- trend


### lstm
- keras
- negative data 제거
- sampling
- seq2seq

### arima
- statsmodels ARIMA
- negative data 제거
- sampling

### xgboost
- xgboost
- negative data 제거

### 제출결과


- 8월 24일

using  | option   | Score
-----  | -------- | -------
arima | 1.0 | 1,599,452
arima | 1.3 | 1,220,402
arima | 1.5 | 1,086,564

- 8월 25일

using  | option   | Score
-----  | -------- | -------
arima | 1.65 | 1,080,924
arima | 1.8 | 1,130,274


- 8월 26일  

2주6개 예측합

using  | option         | Score
------- | --------------- | -------
prophet | 2W6P, CPS0.05, pos | 985,656
prophet | 2W6P, CPS0.5, pos  | 943,433
prophet | 2W6P, CPS0.05, zero | 950,163


- 8월 27일  

지수함수로 감소, 상하한값 두고 logistic regression

using  | option         | Score
------- | --------------- | -------
prophet | 2W6P, CPS0.05exp, logistic | 927,546
prophet | 2W6P, CPS0.5exp, logistic  | 1,002,118


- 8월 28일

MAE기반 피팅 평가함수를 두고 피팅 잘안된경우 CPS 증가  

using  | option         | Score
------- | --------------- | -------
prophet | 2W6P, CPS1to0.5, logistic | 911,445
prophet | 2W6P, CPS10to1, logistic  | 928,103

xgboost: MAE기반 평가함수를 사용. param의 경우 거래일 비율을 각 결과값에 곱해줌. MAPE기반 평가함수 사용.  

using  | option         | Score
------- | --------------- | -------
xgboost | mae, log, pos             | 840,476
xgboost | mae, log, pos, param      | 850,727
xgboost | mape, log, pos            | 838,562


- 마감일 최종 결과

![img](https://github.com/Koo-Koo/dacon-sales-prediction/blob/master/dacon_result_final.JPG)
