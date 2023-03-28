---
title: '[Machine Learning] 12. Optimize(최적화)'
date: 23-02-09 15:13:25 +0800
categories: ['Data Analysis', '05. Machine Learning']
tags: [python, machinelearning, regression]     # TAG names should always be lowercase
use_math: true
---

# 최적화 (Optimize)
- 모델이 예측한 결과와 정답간의 차이(오차)를 가장 적게 만드는 Parameter를 찾는 과정을 최적화라고 한다.
- 모델의 예측값과 실제 값의 차이를 계산하는 함수를 만들고 그 값이 최소가 되는 지점을 찾는 작업을 한다.

## 최적화 문제
- 함수 f(w) 의 값을 최소화(또는 최대화) 하는 변수 w(파라미터)를 찾는 것.
$$
w_{i} = \arg \min_w f(w) 
$$

- `arg`: 최소화 한 변수의 w값


## 경사하강법 (Gradient Descent)
- 다양한 종류의 문제에서 최적의 해법을 찾을 수 있는 **일반적인 최적화 알고리즘**
- 손실함수를 최소화 하는 파라이터를 반복 및 조정을 통해 찾는다.
    - 손실함수의 현재 기울기(gradient)를 계산한다
    - gradient가 감소하는 방향으로 벡터 $W$를 조정한다
    - gradient가 0이 되는 값을 찾는다.
    - (= 미분(변화율)값 == 0 인 순간을 찾는다.)
- gradient가 양수이면 loss와 weight가 비례관계란 의미이므로 loss를 더 작게 하려면 weight가 작아져야 한다.    
- gradient가 음수이면 loss와 weight가 반비례관계란 의미이므로 loss를 더 작게 하려면 weight가 커져야 한다.


- 학습률 (Learning rate)
    - 기울기에 따라 이동할 step의 크기. 경사하강법 알고리즘에서 지정해야하는 하이퍼 파라미터이다.
    - 학습률을 너무 작게 잡으면 최소값에 수렴하기 위해 많은 반복을 진행해야해 시간이 오래걸린다.
    - 학습률을 너무 크게 잡으면 왔다 갔다 하다가 오히려 더 큰 값으로 발산하여 최소값에 수렴하지 못하게 된다.