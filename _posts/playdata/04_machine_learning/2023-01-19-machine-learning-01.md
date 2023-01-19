---
title: '[Machine Learning] 01. Numpy 개요'
date: 23-01-19 12:28:23 +0800
categories: ['Data Analysis', '04. Machine Learning']
tags: [python, numpy, machinelearning]     # TAG names should always be lowercase
---

## NumPy
- <http://www.numpy.org>

- 배열, Numerical Python의 약어
- 벡터, 행렬 연산을 위한 수치해석용 파이썬 라이브러리
    - 강력한 다차원 배열(array) 지원
    - 빠른 수치 계산을 위한 `structured array`, `벡터화 연산`, `브로드캐스팅 기법`등을 통한 다차원 배열과 행렬연산에 필요한 다양한 함수를 제공한다.
    - 파이썬 List 보다 더 많은 데이터를 더 빠르게 처리
    - 기계가 학습할 데이터를 만드는 데 도와준다.
- 많은 과학 연산 라이브러리들이 Numpy를 기반으로 한다.
    - `scipy`, `matplotlib`, `pandas`, `scikit-learn`, `statsmodels`등
    - scipy는 계산, numpy 계산하는 것을 만든다고 생각하면 된다.
    - 그래서 다른 라이브러리를 설치하게 되면 자동으로 설치된다.
- 선형대수, 난수 생성, 푸리에 변환 기능 지원
- 나중에 딥러닝(`pytorch`, `tensor`)의 경우에는 numpy를 사용하지는 않지만 데이터를 다루는 방식이 numpy와 유사하기 때문에 도움이 된다.
