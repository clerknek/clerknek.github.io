---
title: '[Machine Learning] 11. Linear Regression'
date: 23-02-08 15:24:53 +0800
categories: ['Data Analysis', '05. Machine Learning']
tags: [python, machinelearning, regression]     # TAG names should always be lowercase
use_math: true
---

# 선형회귀 개요

선형 회귀(線型回歸, Linear regression)는 종속 변수 y와 한 개 이상의 독립 변수X와의 선형 상관 관계를 모델링하는 회귀분석 기법. [위키백과](https://ko.wikipedia.org/wiki/%EC%84%A0%ED%98%95_%ED%9A%8C%EA%B7%80)

## 선형회귀 모델
- 각 Feature들에 가중치(Weight)를 곱하고 편향(bias)를 더해 예측 결과를 출력한다.
- Weight와 bias가 학습 대상 Parameter가 된다.

$$
\hat{y_i} = w_1 x_{i1} + w_2 x_{i2}... + w_{p} x_{ip} + b
\\
\hat{y_i} = \mathbf{w}^{T} \cdot \mathbf{X} 
$$

- $\hat{y_i}$: 예측값
- $x$: 특성(feature-컬럼)
- $w$: 가중치(weight), 회귀계수(regression coefficient). 특성이 $\hat{y_i}$ 에 얼마나 영향을 주는지 정도
- $b$: 절편
- $p$: p 번째 특성(feature)/p번째 가중치
- $i$: i번째 관측치(sample)

## LinearRegression
- 가장 기본적인 선형 회귀 모델
- 각 Feauture에 가중합으로 Y값을 추론한다.

# 다항회귀 (Polynomial Regression)
- 전처리방식 중 하나로 Feature가 너무 적어 y의 값들을 다 설명하지 못하여 underfitting이 된 경우 Feature를 늘려준다.
- 각 Feature들을 거듭제곱한 것과 Feature들 끼리 곱한 새로운 특성들을 추가한다.
    - 파라미터 가중치를 기준으로는 일차식이 되어 선형모델이다. 파라미터(Coef, weight)들을 기준으로는 N차식이 되어 비선형 데이터를 추론할 수 있는 모델이 된다.
- `PolynomialFeatures` Transformer를 사용해서 변환한다.

- **단항 회귀 결과** **&rarr; Underfitting**
![linear regression](../../../assets/img/playdata/05_machine_learning/11-01.png)

- 단항 회귀의 결과 값을 보면 특정 부분에서는 잘 예측하지만 다른 곳은 예측을 잘 하지 못하는 것을 볼 수 있다.

- **다항 회귀 결과**`degree=2`
![polynomial regression](../../../assets/img/playdata/05_machine_learning/11-02.png)

- 두 결과 값의 차이

    ![Alt text](../../../assets/img/playdata/05_machine_learning/11-03.png)


- 대신 다항회귀에서 Feature 수가 너무 많으면, 즉 **degree를 너무 크게 하면 Overfitting** 문제가 생긴다
- `degree=35`로 정의 했을 때 결과 **&rarr; Overfitting**
![Alt text](../../../assets/img/playdata/05_machine_learning/11-05.png)

- 좀더 가까이서 봤을 때
![Alt text](../../../assets/img/playdata/05_machine_learning/11-04.png)