---
title: '[Computer Vision] 05. Yolo8 Object Detection'
date: 23-03-09 15:52:20 +0800
categories: ['Data Analysis', '08. Computer Vision']
tags: [python, machinelearning, deeplearning, tensorflow, yolo]     # TAG names should always be lowercase
use_math: true
---

# [YOLOv8](https://docs.ultralytics.com/)

## 설치

- `pip install ultralytics`
- 주피터노트북에서 실행할 경우 프로그래스바를 실행하기 위해서 다음을 설치한다. (필수는 아님)
    - `conda install -y -c conda-forge ipywidgets`

## 사용
- CLI (command line interface)에서 터미널 명령어로 추론/평가/학습을 진행할 수 있다.
- Python lib 를 이용해 코드상에 원하는 추론/평가/학습을 진행할 수 있다.