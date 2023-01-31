---
title: '[Machine Learning] 05. 분류 평가지표'
date: 23-01-31 10:27:32 +0800
categories: ['Data Analysis', '05. Machine Learning']
tags: [python, machinelearning]     # TAG names should always be lowercase
use_math: true
---

# 분류와 회귀의 평가방법
### 분류 평가 지표
1. 정확도
2. 정밀도
3. 재현률
4. F1 점수
5. PR Curve, AP score
6. ROC, AUC score

### 회귀 평가방법
1. MSE
2. RMSE
3. ${R^2}$

### scikit-learn 평가함수 모듈
- sklearn.metrics 모듈을 통해 제공

# 분류(Classification) 평가 지표
## 이진 분류(Binary classification)의 양성(Positive)과 음성(Negative)
- 양성(Positive): 모델이 찾으려는(추론하려는) 주 대상
- 음성(Negative): 모델이 찾으려는(추론하려는) 주 대상이 아닌 것
- 예
    - 환자 분류
        - 양성 - 환자, 음성 - 정상인
    - 스팸메일 분류
        - 양성 - 스팸메일, 음성 - 정상메일
    - 금융사기 모델
        - 양성 - 사기거래, 음성 - 정상거래

## 정확도 (Accuracy)
- 대표적인 분류의 평가 지표

$$
\large{
정확도 (Accuracy) = \cfrac{맞게 예측한 건수} {전체 예측 건수}
}
$$

- 전체 예측 한 것중 맞게 예측한 비율로 평가한다.
- `accuracy_score(정답, 모델예측값)`

### Accuracy 평가지표의 문제
- 이진 분류에서 **양성(Positive)에 대한 지표만 확인 할 수 없다.** 
- 불균형 데이터의 경우 정확한 평가지표가 될 수 없다.
    - 예: 양성과 음성의 비율이 1:9 인 경우 모두 음성이라고 하면 정확도는 90%가 된다.