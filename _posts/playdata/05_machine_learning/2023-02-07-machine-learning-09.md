---
title: '[Machine Learning] 08. Ensemble'
date: 23-02-07 09:28:39 +0800
categories: ['Data Analysis', '05. Machine Learning']
tags: [python, machinelearning]     # TAG names should always be lowercase
use_math: true
---

## Ensemble
### Ensemble 이란?
- 여러 모델을 학습시켜 결합하는 방식으로 문제를 해결하는 방식
- 개별로 학습한 여러 모델을 조합해 과적합을 막고 일반화 성능을 향상시킬 수 있다.
- 개별 모델의 성능이 확보되지 않을 때 성능향상에 도움될 수 있다.

### Ensemble 종류
1. 투표방식
    - 여러 개의 Estimatro(추정기)가 낸 결과들을 투표를 통해 최종 결과를 내는 방식
    - 종류
        1. Bagging - 같은 알고리즘, 다른 학습 데이터
            - ex) Random Forest
        2. Voting - 다른 알고리즘
2. Boosting (부스팅)
- 성능이 떨어지는 학습기(Weak Learner)를 결합해서 정확하고 강력한 학습기(Strong Learner)를 만든다.
- 각 약한 학습기들은 순서대로 일을 하며 뒤의 학습기들은 앞의 학습기가 찾지 못한 부분을 추가적으로 찾는다.

## Random Forest
- Bagging 방식의 ensemble 모델
- 다수의 Decision Tree를 사용
    - 여러 개의 Decision Tree를 생성하고 입력데이터를 각각 추론하게 한 뒤 가장 많이 나온 추론결과를 최종결과로 결정한다.
- 처리 속도가 빠르다 & 성능도 높다
    - Random: 학습할 때 Train dataset을 random하게 sampling한다.
    - Forest: 여러개의 (Decision) Tree 모델들을 앙상블한다.

## Boosting model
- 단순하고 약한 학습기(Weak Learner)들를 결합해서 보다 정확하고 강력한 학습기(Strong Learner)를 만드는 방식.
- 약한 학습기들은 앞 학습기가 만든 오류를 줄이는 방향으로 학습한다
- 점점 오차를 줄여 보완하는 형식의 모델

## Gradient Boosting
- 개별 모델로 Decision Tree 를 사용한다.
- depth가 깊지 않은 트리를 많이 연결해서 이전 트리의 오차를 보정해 나가는 방식으로 실행한다.
    - 단순한 모델
    - max_depth 가 최대 5이상을 잡지 않는다.
- 각 모델들은 앞의 모델이 틀린 오차를 학습하여 전체 오차가 줄어들도록 학습한다.
- 얕은 트리를 많이 연결하여 각각의 트리가 데이터의 일부에 대해 예측을 잘 수행하도록 하고 그런 트리들이 모여 전체 성능을 높이는 것이 기본 아이디어.
- 분류와 회귀 둘다 지원하는 모델 (GradientBoostingClassifier, GrandientBoostingRegressor)
- 훈련시간이 많이 걸리고, 트리기반 모델의 특성상 희소한 고차원 데이터에서는 성능이 안 좋은 단점이 있다.

- 훈련 과정 예시 영상

{% include embed/youtube.html id='3CC4N4z3GJc' %}