---
title: '[Machine Learning] 10. Regression(회귀)'
date: 23-02-08 09:19:52 +0800
categories: ['Data Analysis', '05. Machine Learning']
tags: [python, machinelearning, regression]     # TAG names should always be lowercase
use_math: true
---


# Regression
## Regression 이란?
- 예측할 값(Target)이 연속형(continuous) 데이터(float)인 지도 학습(Supervised Learning).
## 회귀(Regression) 평가지표
1. MSE
2. RMSE
3. ${R^2}$

# 회귀(Regression)의 주요 평가 지표
## MSE (Mean Squared Error)
- 실제 값과 예측값의 차를 제곱해 평균 낸 것
- scikit-learn 평가 함수: mean_squared_error()
- 교차검증시 지정할 문자열: 'neg_mean_squared_error'

$$
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y_i})^2\\
y_i: 실제값, \hat{y_i}: 모델이 예측한 값
$$

## RMSE (Root Mean Squared Error)
- MSE는 오차의 제곱한 값이므로 실제 오차의 평균보다 큰 값이 나온다.  MSE의 제곱근이 RMSE이다.
- mean_squared_error() 의 squared=False로 설정해서 계산. 또는 MSE를 구한 뒤 np.sqrt()로 제곱근을 구한다.
- 교차검증시 지정할 문자열: 'neg_root_mean_squared_error'

$$
RMSE = \sqrt{\frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y_i})^2}
$$

## $R^2$ (R square, 결정계수)
- 결정계수는 회귀모델에서 Feature(독립변수)들이 Target(종속변수)를 얼마나 설명하는지를 나타내는 평가지표이다.
    - 평균으로 예측했을 때 오차(총오차) 보다 모델을 사용했을 때 얼마 만큼 더 좋은 성능을 내는지를 비율로 나타낸 값으로 계산한다.
    - 모델은 feature들을 이용해 값을 추론하므로 그 성능은 target에 대한 설명력으로 생각할 수 있다.
- 1에 가까울 수록 좋은 모델.
- scikit-learn 평가함수: r2_score()
- 교차검증시 지정할 문자열: 'r2'
- [참고](https://ko.khanacademy.org/math/statistics-probability/describing-relationships-quantitative-data/assessing-the-fit-in-least-squares-regression/a/r-squared-intuition)

$$
R^2 = \cfrac{\sum_{i=1}^{n}(\hat{y_i}-\bar{y})^2}{\sum_{i=1}^{n}(y_i - \bar{y})^2}\\
R^2 = 1 - \cfrac{\sum_{i=1}^{n}(y_i - \hat{y_i})^2}{\sum_{i=1}^{n}(y_i - \bar{y})^2}
$$

- $y_i$ : i번째 정답 값, 
- $\hat{y_i}$ : i 번째 예측 값, 
- $\bar{y}$ : y의 평균  


## 평가지표 비교
- 대부분의 평가 지표 `ex) accuracy` 는 값이 클수록 좋은 평가를 얻는다
- 하지만 회귀의 경우에는 error를 계산하는 것이기 때문에 값이 작을 수록 좋은 평가를 받아야 한다.