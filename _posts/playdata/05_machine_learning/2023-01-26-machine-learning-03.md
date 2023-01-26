---
title: '[Machine Learning] 03. 데이터셋 나누기와 교차 검증'
date: 23-01-26 12:37:23 +0800
categories: ['Data Analysis', '05. Machine Learning']
tags: [python, machinelearning]     # TAG names should always be lowercase
---

## 데이터 셋
- **Train 데이터셋 (훈련/학습 데이터셋)**
    - 모델을 **학습**시킬 때 사용할 데이터셋.
    - 옛날 데이터(Train Data)를 이용해서 새로운 데이터 추론

- **Validation 데이터셋 (검증 데이터셋)**
    - 모델의 성능 **중간 검증**을 위한 데이터셋
    - Test set과 Train set만 사용해서 `설정변경 -> 훈련 -> 평가`를 반복하게 되면 Test set에 모델이 맞춰지기 때문에 모델의 성능을 제대로 평가할 수 없게 된다.
    - 따라서 데이터 셋을 Train set, Validation set, Test set으로 나눠 **Train set과 Validation set으로 모델을 최적화** 한뒤 마지막에 **Test set으로 최종 평가**한다.

- **Test 데이터셋 (평가 데이터셋)**
    - 모델의 **성능을 최종적으로 측정**하기 위한 데이터셋
    - **Test 데이터셋은 마지막에 모델의 성능을 측정하는 용도로 한번만 사용되야 한다.**
        - 만약 원하는 성능이 나오지 않는다면 데이터나 하이퍼 파라미터를 변경한 뒤 다시 훈련시켜야 한다. -> **Hyper Parameter Tuning**

![Dataset train](../../../assets/img/playdata/05_machine_learning/03_01.png)