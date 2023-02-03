---
title: '[Machine Learning] 07. 지도학습'
date: 23-02-03 15:19:43 +0800
categories: ['Data Analysis', '05. Machine Learning']
tags: [python, machinelearning, knn, svm]     # TAG names should always be lowercase
use_math: true
---

# KNN
## KNN이란?
- K-최근접 이웃 (K-NearestNeighbors)
- Classification(분류)과 Regression(회귀)를 모두 지원한다
    - Classification은 가장 가까운 K **원소 종류의 개수**로 계산
    - Regression은 가장 가까운 K **원소 값의 평균**으로 계산
- 예측하려는 데이터와 주위에 있는 데이터의 거리를 측정해 **가장 가까운 K개의 데이터**를 참조해 분류 예측한다.
- 학습시 단순히 데이터를 저장하고 **예측 시점에 거리를 계산**한다.
    - 학습은 빠르지만 예측시 시간이 많이 걸린다.
## K (Hyper Parameter)
- K는 새로운 데이터포인트를 분류할때 확인할 데이터 포인트의 개수를 지정하는 hyper parameter이다.

![knn](../../../assets/img/playdata/05_machine_learning/07-01.png)


- **분류****
    - K를 1로 하면 <font color='blue'>파란색</font>, K를 3으로 하면 <font color='orange'>주황색</font> 으로 분류한다.
- ****회귀****
    - K를 1로 하면 <font color='blue'>파란색</font>, K를 3으로 하면 <font color='orange'>주황색</font> data point의 평균값으로 추론한다.
- K가 너무 **작으면 Overfitting**이 일어날 수 있고 K가 너무 **크면 Underfitting**이 발생할 수 있다.
    - Overfitting: K값을 더 크게 잡는다.
    - Underfitting: K값을 더 작게 잡는다

## 주요 Hyper Parameter

- **분류: sklearn.neighbors.KNeighborsClassifier**,  **회귀: sklearn.neighbors.KNeighborsRegressor**
- 이웃 수 
    - n_neighbors = K
    - n_neighbors는 Feature수의 제곱근 정도를 지정할 때 성능이 좋은 것으로 알려져 있다.
- 거리 재는 방법 
    - p=2: 유클리디안 거리(Euclidean distance - 기본값 - L2 Norm)
        - 제곱을 통해 거리계산 **&rarr;** 대각선
    - p=1: 맨하탄 거리(Manhattan distance - L1 Norm)
        - 일반 거리로 거리계산 **&rarr;** 네모

> ### 유클리디안 거리(Euclidean_distance)
![euclidean](../../../assets/img/playdata/05_machine_learning/07-02.png)

$$
distance = \sqrt{(a_1 - b_1)^2 + (a_2-b_2)^2}\\
n차원 벡터간의 거리 = \sqrt{(a_1 - b_1)^2 + (a_2-b_2)^2 +...+(a_n-b_n)^2}
$$

> ### 맨하탄 거리 (Manhattan distance)
![manhattan](../../../assets/img/playdata/05_machine_learning/07-03.png)

$$
distance = |a_1 - b_1| + |a_2 - b_2| \\
𝑛차원벡터간의거리= |a_1 - b_1| + |a_2 - b_2| + ... + |a_n - b_n|
$$

## 요약
### 장점
- 이해하기 쉬운 모델이며 튜닝할 하이퍼파라미터의 수가 적어 빠르게 만들 수있다.

### 단점
- 훈련세트가 너무 큰 경우(Feature나 관측치의 개수가 많은 경우) 거리를 계산하는 양이 늘어나 예측이 느려진다.
    - 추론에 시간이 많이 걸린다.
- Feature간의 값의 단위가 다르면 작은 단위의 Feature에 영향을 많이 받게 되므로 전처리로 **Feature Scaling작업**이 필요하다.
- Feature가 너무 많은 경우와 대부분의 값이 0으로 구성된(희소-sparse) 데이터셋에서 성능이 아주 나쁘다


### 사용처
- K-NN은 서비스할 모델을 구현할때 보다는 복잡한 알고리즘을 적용해 보기 전에 확인용 또는 base line을 잡기 위한 모델로 사용한다.
    - 주로 K-NN 결과 보다 더 좋은 모델을 만들어야 한다.(기준)