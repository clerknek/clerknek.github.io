---
title: '[Computer Vision] 07. Pose Estimation'
date: 23-03-13 16:09:35 +0800
categories: ['Data Analysis', '08. Computer Vision']
tags: [python, machinelearning, deeplearning, tensorflow]     # TAG names should always be lowercase
use_math: true
---

## Pose Estimation
- 영상에서 사람의 관절을 검출하여 자세를 추정하는 컴퓨터 비전 분야.
    - 추정하는 관절은 모델마다 조금씩 다르나 머리, 목, 어깨, 팔꿈치, 손, 엉덩이, 무릎, 발목 등을 찾는다.
- 스포츠 분야 자세분석, 이상행동 탐지등 사람의 자세를 응용한 서비스에 적용될 수 있다.

### 분류
- Single person, Multi person
    - 영상내의 한명의 자세만 추정하는지 여러명의 자세를 추정하는지에 따른 구분
- Direct Regression, Heatmap based
    - 관절 keypoint 추정하는 방식에 따른 분류
- Top-Down, Bottom-up
    - 모델이 image를 처리하는 순서/방식에 따른 분류

### Direct Regression, Heatmap based
- Pose estimation은 사람이 어떤 자세를 취하고 있는지 알 수 있도록 인체의 관절들의 좌표를 찾는다. 이 추정할 좌표를 모델이 추정하는 방식으로 Direct Regression, Heatmap based

#### Direct Regression 방식
- 회귀방식으로 각 관절의 x, y 좌표를 직접 찾는 방식이다. 

#### Heatmap based 방식
- 관절 Keypoint를 pixel 단위로 keypoint가 위치할 가능성을 표현하는 heatmap(confidence map)으로 변환한 뒤에 학습/추정하는 방식. 
- 관절 keypoint가 위치한 중심점은 가장 확률이 높으며 멀어질수록 작은 확률 값을 가져 heatmap 형태가 된다.
- 학습을 시킬때 keypoint를 heatmap으로 변환시킨 뒤 학습을 시킨다. 모델은 각 관절 keypoint들을 heatmap형태로 출력하며 그것을 다시 keypoint로 변환해서 최종 추론 결과를 만든다.

### Top-Down, Bottom-up 방식
#### Top-Down 방식
- 이미지에서 사람을 먼저 탐지(Detection) 한 뒤 각 사람의 자세를 추정한다.
    - 사진에 여러사람이 있는 경우 각각의 사람들을 탐지 한 뒤 한사람씩 pose 추정을 수행한다. (single person pose estimation)
- 이미지에 사람이 많은 경우 각각의 사람에 대해 순차적으로 알고리즘을 적용하기 때문에 더 많은 시간을 소비한다.
    
#### Bottom-Up 방식
- 이미지에 포함된 사람들의 관절부분(Keypoints)를 먼저 찾아내고 연결해서 사람의 자세를 추정한다.
    - Top-Down의 반대되는 방식
- keypoints를 바로 찾기 때문에 정확도는 Top-Down방식보다 떨어지지만 속도가 빠르다. 
    - 찾은 관절을 매칭할 수 있는 조합이 매우 많아 이를 적절하게 매칭하는데 정확도가 낮다.

## MoveNet을 이용한 Pose 추정
- Google Research에서 공개한 pose 추정 모델.
- 데스크탑, 노트북, 휴대폰 등의 일반적인 환경에서도 좋은 속도와 성능을 내는 것을 특징으로 한다.
- 다음 두가지 버전의 모델을 제공
    - Thunder: 높은 정확도를 필요로하는 application을 위한 모델
    - Lightning: 처리시간(빠른 처리)이 중요한 application을 위한 모델
- 또한 single pose 모델과 multi pose 모델을 제공한다.
    - multipose 모델은 최대 6명까지 검출한다.
- 모든 모델은 Tensorflow hub를 통해 제공한다.
    - Tensorflow 버전, TFLite 버전, Tensorflow.js 버전을 제공한다.
- [Tutorial](https://www.tensorflow.org/hub/tutorials/movenet)
- [라이브데모](https://storage.googleapis.com/tfjs-models/demos/pose-detection/index.html?model=movenet)
    
### Tensorflow hub
- Tensorflow hub는 각 분야의 미리학습된 모델들의 저장소이다. 
- 서비스를 위한 완성된 모델이나 transfer learning을 위한 모델에 tensorflow hub에서 제공하는 모델을 간단한 코드 몇줄로 쉽게 적용할 수 있다.
- <https://www.tensorflow.org/hub/tutorials?hl=ko>
- 모델 검색: <https://tfhub.dev/>

## 작성함수
- preprocess()
    - 매개변수로 받은 영상을 모델이 추론할 수 있도록 전처리
    - 전처리
        - resize
            - movenet thunder: 32배수 크기로 resize. 최대 256이되지 않도록 한다.
            - movenet lightning: 32배수 크기로 resize. 최대 192가 되지 않도록 한다.
        - type: int32로 변환한다.
- get_model()
    - tensorflow hub에서 Movenet 모델을 다운받아 리턴하는 함수
- draw_keypoints()
    - 모델이 찾은 keypoints(관절)을 원본 이미지 영상에 표시한다.
- draw_edges()
    - keypoint들을 연결하는 것을 원본 이미지에 표시한다.
- detect_image()
    - 이미지 영상으로 부터 추론
- detect_video()
    - 동영상으로 부터 추론