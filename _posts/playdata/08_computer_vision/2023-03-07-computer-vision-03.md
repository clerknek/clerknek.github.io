---
title: '[Computer Vision] 03. TFRecord'
date: 23-03-07 09:20:51 +0800
categories: ['Data Analysis', '08. Computer Vision']
tags: [python, machinelearning, deeplearning, tensorflow]     # TAG names should always be lowercase
use_math: true
---

# TFRecord

- Train/Test/Validation Dataset을 하나의 파일로 디스크(HDD)에 저장하는 Tensorflow 파일저장형식.
    - Train 시 파일로 저장된 Raw 데이터를 모델에 입력할 때 **데이터 입력, Label parsing**하는 것이 학습 속도를 떨어트리는 원인이 된다.
        - batch size 만큼의 이미지 파일을 읽어 들이면 batch size만큼의 파일 입력작업이 발생한다.
        - annotation 파일에서 정답(y)값을 parsing 하는 것도 속도 저하의 원인이 된다.
    - Tensorflow에서 학습시 데이터셋을 읽어들이는 속도를 향상시키기 위해 데이터들에 Serialization을 수행해서 하나의 파일로 저장할 수 있는 TFRecord 파일 포맷을 제공한다.
    - 파일의 용량이 너무 크면 여러 파일로 자를 수 있다.
        - 한 파일을 강제적으로 자른 것
        - 100장의 데이터가 들어가 있는 파일을 100개로 자른다고 해서 1장의 사진이 나오는 것이 아님
- <https://www.tensorflow.org/tutorials/load_data/tfrecord>

> - **직렬화(Serialization):** 메모리에 저장된 다양한 타입의 값을 디스크(네트워크)에 저장할 수 있는 상태로 변환하는 것.
> - **binary data:** 디스크에 저장되는 0, 1로 구성된 데이터

- tf.train.Example
    - 하나의 데이터 포인트를 TFRecord에 저장하기 위해 변환하는 타입. 하나의 데이터포인트를 tf.train.Example 의 객체로 변환해서 직렬화 한 뒤 저장한다.

- tf.train.Feature
    - 하나의 데이터를 구성하는 속성(feature)들을 변환하는 클래스.
    - tf.train.Feature는 다음 세가지 타입을 지원한다.
        - tf.train.BytesList – string, bytes 타입을 변환
        - tf.train.FloatList –  float(float32), double(float64) 타입을 변환
        - tf.train.Int64List –  int, uint, bool, enum 타입을 변환

- tf.train.Example의 형태
```python
{
    "feature명":tf.train.Feature타입객체,
    "feature명":tf.train.Feature타입객체,
    ...
}
```
## Example 생성 예제
- 문자열을 key로 Feature를 값으로 가지는 dictionary를 이용해 생성


## Feature 직렬화 예제
- Feature객체/Example객체.SerializeToString()
    - 각 Featuer(Feature객체를 통해 호출), Example의 Feature들(Example객체를 통해 호출)을 파일로 출력할 수 있도록 직렬화(bytes로 변환) 한다.
        - Feature객체->bytes 로 변환
    - tfrecord 파일로 출력하기 전에 Example의 Feature들은 직렬화 되어야 한다.