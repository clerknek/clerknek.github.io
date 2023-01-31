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

- 정밀도, 재현률 F1 점수 -> Positive에 대한 평가 지표

### 회귀 평가방법
1. MSE
2. RMSE
3. ${R^2}$

### scikit-learn 평가함수 모듈
- sklearn.metrics 모듈을 통해 제공

# 분류(Classification) 평가 지표
## 이진 분류(Binary classification)의 양성(Positive)과 음성(Negative)
- 양성(Positive)-1: 모델이 찾으려는(추론하려는) 주 대상
- 음성(Negative)-0: 모델이 찾으려는(추론하려는) 주 대상이 아닌 것
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

- 전체 대비 맞은 예측 값 비율로 평가한다.
- `accuracy_score(정답, 모델예측값)`

### Accuracy 평가지표의 문제
- 이진 분류에서 **양성(Positive)에 대한 지표만 확인 할 수 없다.** 
- 불균형 데이터의 경우 정확한 평가지표가 될 수 없다.
    - 예: 양성과 음성의 비율이 1:9 인 경우 모두 음성이라고 하면 정확도는 90%가 된다.



## 혼동 행렬(Confusion Marix)
- 실제 값(정답)과 예측 한 것을 표로 만든 평가표
    - 분류의 예측 결과가 몇개나 맞고 틀렸는지를 확인할 때 사용한다.
- 함수: confusion_matrix(정답, 모델예측값)
- 결과의 0번축(True, False): 실제 class, 1번 축(Positive, Negative): 예측 class -> Scikit learn 기준

![Confusion Matrix](../../../assets/img/playdata/05_machine_learning/05_01.png)

- **TP(True Positive)** 
    - 양성으로 예측했는데 맞은 개수
- **TN(True Negative)** 
    - 음성으로 예측했는데 맞은 개수
- **FP(False Positive)** 
    - 양성으로 예측했는데 틀린 개수 
    - 음성을 양성으로 예측
- **FN(False Negative)** 
    - 음성으로 예측했는데 틀린 개수 
    - 양성을 음성으로 예측

- 예)
```python
[[20, 6],
 [4, 40]]
```