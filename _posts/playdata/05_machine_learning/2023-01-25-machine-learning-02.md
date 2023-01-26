---
title: '[Machine Learning] 02. 머신러닝 기본 순서'
date: 23-01-25 12:37:23 +0800
categories: ['Data Analysis', '05. Machine Learning']
tags: [python, machinelearning, sklearn]     # TAG names should always be lowercase
---

## 머신러닝 순서

1. 데이터 셋 불러오기
2. 독립변수(= input data = Features) 와 종속변수(= output data = labels = Targets)을 X와 y로 설정
3. X, y(전체 데이터셋)을 Train dataset과 Test dataset으로 분리 -> sklearn의 train_test_split() 함수를 사용하면 편리하게 분리 가능
    ```python
    train_test_split(X, # 전체데이터셋중 Features, input
                    y, # 전체데이터셋중 labels, output, target
                    test_size = 0.2, # 전체중 test set의 비율(기본값:0.25) -> 정수로 하면 개수
                    stratify=y, # 전체 데이터셋의 출력 클래스의 비율과 동일한 비율로 나눠지도록 한다. 분류 Dataset을 나눌때 필수, (회귀는 하지 않음)
                    shuffle=True, # 데이터셋을 나누기 전에 섞는지(랜덤) 여부: True- 섞는다(기본값), False-안섞는다.
                    random_state=0 # random seed 값
                    )
    ```
4. 모델 생성
    - 모델을 생성할 때 모델별로 매개변수가 있는 데 이 매개변수에 의해 모델 성능에 차이가 생길 수 있다. -> **Hyper Parameter(사용자가 정해주는 값)**
    - ex) DecisionTreeClassifier의 max_depth
5. Train set을 이용해서 모델 학습
6. 평가
    - 머신러닝 평가지표 함수들은 sklearn.metrics 모듈에 있다.