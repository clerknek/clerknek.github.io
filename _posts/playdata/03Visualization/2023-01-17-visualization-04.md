---
title: '[Visualization] 04. Seaborn'
date: 23-01-17 14:23:14 +0800
categories: ['Data Analysis', '03. Visualization']
tags: [python, matplotlib, seaborn]     # TAG names should always be lowercase
---


## Seaborn
- matplotlib을 기반으로 다양한 테마와 그래프를 제공하는 파이썬 시각화 패키지.
- 기본적으로 toy data(테스트 해볼 수 있는 데이터) 를 제공해준다.
- 데이터프레임과의 연동이 잘 되어 있다. <-> matplotlib: 그래프를 그리기 위해 데이터를 사용자가 직접 지정해주어야 함


- 모듈 설치: 아나콘다에는 기본적으로 포함되어 있다.
    `!pip install seaborn`
- 모듈 사용
    ```python
    import seaborn as sns
    import matplotlib.pyplot as plt

    tips = sns.load_dataset('tips') # tips라는 toy data를 불러옴
    ```

## rugplot, kdeplot, displot
- 1차원 연속형 값들의 분포를 시각화 하는 그래프
### rugplot()
- 각 데이터들의 위치를 보여준다.

- 기본 구문
    ```python
    sns.rugplot(tips['total_bill'])
    ```

- x="컬럼명", data: DataFrame 형식
    ```python
    sns.rugplot(x='total_bill', data=tips)
    ```

### kdeplot()
- KDE를 그려줌
    - KDE(Kernel Density Estimation): 확률 밀도 추정
- 구문 예제
    ```python
    sns.kdeplot(x='total_bill', data=tips)
    ```

### displot()
- 히스토그램을 기준으로 rugplot, kdeplot을 같이 그릴 수 있다
- 위 2개 보다 많이 씀

- 구문 예시
    ```python
    sns.displot(x='total_bill', data=tips)
    ```
- 추가 설정
    - `rug = True`: displot 위에 rugplot 보여주기
    - `kde = True`: displot 위에 kdeplot 보여주기
    - `hue = ''`: 원하는 그룹으로 나눠서 보여주기 (= groupby())

## boxplot, violinplot, swamplot
- 연속형 데이터(양적데이터)들의 분포를 확인하는 그래프를 그린다.
- 범주별로 연속형 데이터의 분포를 비교할 수 있다.

### boxplot()
- 구문 예시
```python
sns.boxplot(x='total_bill', data=tips)
```  

### violinplot()
- boxplot위에 분포 밀도(kernel density)를 좌우 대칭으로 덮어쓰는 방식의 그래프 -> kde 그래프를 boxplot 좌우로 붙인 모양
- 매개변수는 boxplot과 동일
- 구문 예시
```python
sns.violinplot(y='tip', data=tips)
```  

### swapplot()
- 실제 값에 점을 찍어 준다.
- boxplot나 violin plot을 보안해준다.
- 좀더 정확하게 값이 어디있는지 알 수 있다.
- 단독으로는 잘 안쓰고 boxplot나 violin plot위에 그린다
- 구문 예시
```python
sns.boxplot(y = 'tip', data = tips, color='r')
sns.swarmplot(y = 'tip', data = tips)

```

### 여러가지 값을 한 그래프로 표현
- 1. y로(y가 있을 때는 x로) 먼저 나눈다.
- 2. hue를 이용해 또 나눈다
- 예시 코드
```python
sns.boxplot(x = 'total_bill',
        y = 'smoker',
        hue = 'sex',
        data = tips)
```  

## 한개의 figure에 2개 이상의 그래프 그리기

- 구문 예시
```python
fig = plt.figure(figsize=(15, 10))
ax1 = fig.add_subplot(1, 2, 1)
ax2 = fig.add_subplot(1, 2, 2)

sns.boxplot(x='total_bill', data=tips, ax=ax1)
sns.boxplot(y='tip', data=tips, ax=ax2)
plt.show()
```

- 아래 코드로도 같은 그래프가 만들어진다.

```python
plt.figure(figsize=(15, 10))
plt.subplot(1, 2, 1)
sns.boxplot(x='total_bill', data=tips)

plt.subplot(1, 2, 2)
sns.boxplot(y='tip', data=tips)
plt.show()
```

## countplot()
- 막대그래프(bar plot)을 그리는 함수
- 범주형 변수의 고유값의 개수를 표시
- matplotlib의 bar()

- 구문 예시
```python
sns.countplot(x='day', data=tips)
```

- 추가 설정
    - `hue=''`: ~ 별로 나눠서 시각화
    - `dodge=False`: 수평누적막대 그래프