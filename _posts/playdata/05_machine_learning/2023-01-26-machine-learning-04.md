---
title: '[Machine Learning] 04. 데이터 전처리'
date: 23-01-26 15:45:23 +0800
categories: ['Data Analysis', '05. Machine Learning']
tags: [python, machinelearning, preprocessing]     # TAG names should always be lowercase
---

## Data Preprocessing
- 데이터를 가지고 머신러닝을 진행하기 위해서는 좋은 데이터를 가지고 해야 결과값이 잘 나온다.
    - Garbage in, Garbage out
- 비정형 데이터의 경우에는 데이터 구조가 정해져 있지 않기 때문에 오랫동안 발전을 못하다가 딥러닝이 발달되면서 발전이 되기 시작했다.
- 목적
    1. 학습이 가능한 데이터셋을 만들기 위한 전처리
        - 머신러닝 알고리즘은 숫자만 처리할 수 있다.
        - 따라서 결측치, 문자열이 있으면 학습이나 추론을 할 수 없다.
        
    2. 학습이 더 잘되도록 만들기 위한 전처리
