---
title: '[Deep Learning] 09. 주요 CNN 모델'
date: 23-02-28 09:45:35 +0800
categories: ['Data Analysis', '07. Deep Learning']
tags: [python, machinelearning, deeplearning, tensorflow]     # TAG names should always be lowercase
use_math: true
---

# GlobalAveragePooling (GAP)

![Alt text](../../../assets/img/playdata/07_deep_learning/09-01.png)

- 입력 Feature map의 채널별로 평균값을 추출하여 1 x 1 x channel 의 Feature map을 생성하는 Pooling
- **Flatten** 대신 사용한다 &rarr; 3차원을 1차원으로 줄여줌 
    - Flatten의 경우에는 Weight가 너무 많이 발생한다
        - 7*7*512를 512 Dense에 넣을 때의 weight
            - Flatten의 경우: 7*7*512*512
            - GAP의 경우: 512*512
    - **Feature map의 채널수가 많을 경우 GAP를 사용하는 것이 효과적이나 채널수가 적다면 Flatten을 사용하는 것이 좋다.**
- `model.add(keras.layers.GlobalAveragePooling2D())`

# Pretrained Model
- 다른 목적을 위해 미리 학습된 모델.
- 사용하는 이유: 딥러닝을 하는 데 시간과 돈이 많이 들기 때문에 사용
- Pretrained model을 좀 더 학습시켜 새로운 네트워크 모델에 적용시키는 방식을 **Transfer Learning (전이 학습)**이라고 한다.

## Keras에서 제공하는 Pretrained Model 
- tensorflow.keras.applications 패키지를 통해 제공
    - https://www.tensorflow.org/api_docs/python/tf/keras/applications?hl=ko
    - Modules
        - 각 모델별 입력 Image 전처리 함수 제공
    - Functions
        - 각 모델 생성함수
- 모델 생성함수의 주요 매개변수
    - `weights`: 모델의 학습된 weight 지정. 
        - 기본값- 'imagenet'. ImageNet 데이터셋으로 학습된 weight를 가진 모델 생성
    - `include_top`: fully connected layer(분류기)를 포함할지 여부. True 포함시킴, False: 포함 안 시킴
        - False를 지정하면 Feature Extractor인 Convolution Layer들로만 구성된 모델이 생성된다.
    - `input_shape`: Input(입력) 이미지의 크기 shape. 3D 텐서로 지정. (높이, 너비, 채널). 기본값: (224,224,3)

> 딥러닝 모델기반 application 개발시 대부분 Transfer Learning을 한다.  
> 다양한 분야에서 다양한 네트워크 모델들이 구현되어 공개 되어 있으며 학습된 Parameter들도 제공되고 있다.  
> [paperswithcode](https://paperswithcode.com/)에서 State Of The Art(SOTA) 논문들과 그 구현된 모델을 확인할 수 있다. 

> **State Of The Art(SOTA)**: 특정 시점에 특정 분야에서 가장 성능이 좋은 모델을 말한다.