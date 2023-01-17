---
title: '[Visualization] 03. Pandas 시각화'
date: 23-01-17 09:25:11 +0800
categories: ['Data Analysis', '03. Visualization']
tags: [python, matplotlib, pandas]     # TAG names should always be lowercase
---

## 01. Pandas 시각화
- Pandas 자체적으로 matplotlib 를 기반으로 한 시각화기능을 지원한다. -> 그래프를 생성한 이후 설정할 때 matplotlib을 사용해도 된다.
- Series나 DataFrame에 plot() 함수나 plot accessor를 사용한다.
    - accessor: 다른 타입에만 사용할 수 있는 메소드를 사용할 수 있도록 연결해주는 역할 
        - ex) str, dt, plot
    - 기본구문
        - plot() 함수
            - `(Series/DataFrame).plot(kind='그래프종류')`
        - plot accessor
            - `(Series/DataFrame).plot.그래프함수()`
- matplotlib에서 사용한 설정을 그대로 사용할 수 있다.

- <https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html>


### Pandas 시각화 예시
#### matplotlib

```python
plt.figure(figsize=(4,3)) # 버전이 업그레이드 되면서 밖에서도 설정할 수 있다.
s.plot(kind='bar')
plt.title('과일 수량') # matplotlib으로 설정
plt.xlabel("과일")
plt.ylabel('수량')
plt.show()
```

#### plot()


```python
s.plot(kind='bar', title='과일 수량', xlabel='과일종류', ylabel='개수', figsize=(4,3))  # 판다스
plt.show()
```

#### plot accessor

```python
s.plot.bar(title='과일 수량', xlabel='과일종류', ylabel='개수', figsize=(4,3))
plt.show()
```

### Bar plot(막대 그래프)
- 기본구문
    ```python
    자료구조.plot(kind='bar')
    자료구조.plot.bar()
    ```
- 추가 설정
    - `kind='barh'`: 수평 막대 그래프
    - `stacked=True`: 값이 쌓여있는 형태의 그래프를 보여주는 설정
    - `subplots=True`: 각 값들의 결과값을 따로 보여주는 설정


### Pie chart(파이차트)
- 기본구문
    ```python
    자료구조.plot(kind='pie')
    자료구조.plot.pie()
    ```
    
    - 자료구조 형식
        - index: label
        - value: 비율계산


### Histogram(히스토그램), KDE(밀도그래프)
#### Histogram(히스토그램)
- 기본구문
    ```python
    자료구조.plot(kind='hist')
    자료구조.plot.hist()
    ```

#### KDE(밀도그래프)

- 모듈 설치: `!pip install scipy`

- 기본구문
    ```python
    자료구조.plot(kind='kde')
    자료구조.plot.kde()
    ```

### Boxplot (상자그래프)

- 기본구문
    ```python
    자료구조.plot(kind='box')
    자료구조.plot.box()
    ```

### Scatter plot (산점도)

- 다른 그래프들과는 다르게 2개의 컬럼들(DataFrame)을 이용해서 그린다. (Series는 그릴 수 없다.)

- 기본구문
    ```python
    자료구조(DF).plot(kind='scatter')
    자료구조(DF).plot.scatter()
    ```
