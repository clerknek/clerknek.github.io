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


## Numpy의 데이터 구조
- **Scalar (스칼라)**
    - 값 하나
- **Vector (백터)**
    - 여러개의 값들을 순서대로 모아놓은 데이터 모음(데이터 레코드)
    - 1D Tensor, 1D Array (1차원 배열)
- **Matrix (행렬)**
    - 벡터들을 모아놓은 데이터 집합. 2개의 방향으로 값들이 관리된다.
    - 2D Tensor, 2D Array (2차원 배열)
- **Tensor (텐서)**
    - 같은 크기의 행렬들(텐서들)을 모아놓은 데이터 집합. N개의 방향으로 값들이 관리된다.
    - ND Tensor, ND Array (다차원 배열)

### 용어
- 축 (axis)
    - 값들의 나열 방향
    - 하나의 축(axis)는 하나의 범주(분류, Category)이다.
- 랭크 (rank)
    - 데이터 집합에서 축의 개수
    - 차원 (dimension) 이라고도 한다
- 형태/형상 (shape)
    - 각 축(axis) 별 데이터의 개수
    - 주로 tuple로 형태를 알려준다.
    - 예시) 이미지를 사용할 때 shape 순서들이 다른데 이것을 이해하는 것이 중요하다.
        - Tensorflow (사진 개수, 가로, 세로, 3 `-> rgb`)
        - Pytorch(사진 개수, 3, 가로, 세로)
- 크기 (size)
    - 배열내 원소의 총 개수

![01_01.png](/assets/img/playdata/04_machinelearning/01_01.png)
_출처: <https://www.oreilly.com/library/view/elegant-scipy/9781491922927/ch01.html>_


## ndarray (넘파이 배열)

## 배열 생성 함수

### array()
- 구문 예시
    ```python
    array(배열형태 객체 [, dtype])
    ```
#### 데이터 타입(dtype)
- 원소들의 데이터 타입
- ndarray.dtype 속성을 이용해 조회
- ndarray.astype(데이터타입)
    - 데이터타입 변환하는 메소드
    - 변환한 새로운 ndarray객체를 반환
    - 데이터 타입을 변환할때 큰 데이터 타입에서 작은 데이터 타입으로 바뀌면 값이 바뀔 수도 있으니 주의해야 한다.


#### + array.size vs len(array)
- array.size: array 안의 데이터 개수
- len(array): array 안의 원소 개수
- 예시 코드
    ```python
    a1 = np.array([[1, 2], [2, 3]])
    print("array.size 개수:", a1.size) # 배열.size - 전체 원소 개수
    print("len(array) 개수:", len(a1)) # len(배열) - 0축 size
    ```
- 예시 코드 결과 값
    ```
    array.size 개수: 4
    len(array) 개수: 2
    ```
