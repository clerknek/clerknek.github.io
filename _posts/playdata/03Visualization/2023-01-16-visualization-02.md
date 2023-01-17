---
title: '[Visualization] 02. matplotlib을 활용한 그래프 그리기'
date: 23-01-16 09:29:00 +0800
categories: ['Data Analysis', '03. Visualization']
tags: [python, matplotlib]     # TAG names should always be lowercase
---

## 1. 선 그래프(line plot) 그리기
### 선 그래프(꺾은 선 그래프)
- **점과 점을 선으로 연결한 그래프**
-  Line plot를 그리는 이유
    - 값의 **변화**를 시각적으로 표현할 때 사용(시계열)
- `plt.plot(x, y)` 또는 `axis.plot(x, y)`
    - x, y 인수
        - 리스트
        - 튜플
        - numpy 배열 (ndarray)
        - 판다스 Series

- 사용할 모듈
```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
```

### 설정
> <https://matplotlib.org/3.0.3/gallery/lines_bars_and_markers/line_styles_reference.html>


- linestyle: 선의 모양 `('.', '--', ':', '-.')`
- linewidth: 선의 두께
- marker: 값이 위치한 곳에 찍어줄 포인트
- color: 선의 색상
- alpha: 선의 투명도
- label: 선에 라벨 값 붙이기 -> 나중에 lengend()를 사용하면 선 이름이 보임


```python
x = np.linspace(1, 10, num=20) # 1 ~ 10을 20등분(num)한 분위 값으로 이뤄진 1차원 배열을 생성. 
                                # -> 리스트나 시리즈 같이 다양한 자료구조로 변환할 수 있다. (1차원의 자료구조)

# plt 함수를 이용해서 선그래프 그리기
plt.plot(x, x)                                  # 기본 그래프
plt.plot(x, x+1, linestyle ='--')               # 선 모양 변경
plt.plot(x, x+2, marker='.', color='red')       # 값이 위치한 곳 표시 & 색상 변경
plt.plot(x, x+3, linestyle ='-.', linewidth=5)  # 선 두께 변경
plt.show()
```

### Twin
- 값의 범위(Scale)이 다른 두 값과 관련된 그래프를 한 Axes(subplot)에 그리는 경우 사용
- 같은 그래프인 것처럼 보이지만 실제로는 다른 그래프에서 그린 후에 합친 것이기 때문에 비교를 위한 설정을 따로 해주어야 한다.
- X축을 공유해 2개의 Y축을 가지는 그래프
    - axes.twinx() 를 이용해 axes를 복사
- Y축을 공유해 2개의 X축을 가지는 그래프
    - axes.twiny() 를 이용해 axes를 복사

### legend 위치 선정

- 미리 지정된 위치로 잡기.
    - legend(loc="상하위치 좌우위치")
        - 상하: upper, center, lower
        - 좌우: left, center, right
        - 정가운데: "center"
        - "best":최적의 위치를 알아서 잡아준다.(Default)
- 원하는 위치를 직접 설정
    - legend(bbox_to_anchor=(x, y), loc="box의 상하, 좌우 위치")
    - bbox_to_anchor
        - 전체 subplot의 x축과 y축의 비율
        ```
        하단: (0, 0), (1, 0)
        상단: (0, 1), (1, 1)
        ```
    - loc -> bbox_to_anchor 좌표지정 범례 box의 어느 지점을 붙일 것인지 지정
        - ex) bbox_to_anchor=(1, 1), loc='upper left' : subplot (1, 1) 지점의 범례박스 위/왼쪽 점을 맞춘다.

## 2. 산점도(Scatter Plot) 그리기
### 산점도(산포도)
- **관측값들이 점으로 표시된 그래프**
- Scatter plot를 사용하는 이유
    - 두 변수(Feature)간의 **관계**를 보기 위해 사용 -> 군집 분류
- `plt.scatter(x, y)` 또는 `axis.scatter(x, y)`
    - x, y 인수
        - 리스트
        - 튜플
        - numpy 배열 (ndarray)
        - 판다스 Series

### 설정
> <https://matplotlib.org/stable/api/markers_api.html>

- marker: 점의 모양
- s: 점의 크기(정수)
- alpha: 점의 투명도 (0 ~ 1 사이 실수, Default 1)


### 상관 계수
- 두 변수간의 상관관계(비례/반비례)를 정량적(수치적)으로 계산한 값.
    - 양수: 비례관계(양의 상관관계)
        - 0 ~ 1
    - 음수: 반비례관계(음의 상관관계)
        - -1 ~ 0
    - 절대값 기준 1로 갈수록 강한 상관관계, 0으로 갈수록 약한 상관관계
        - 1 ~ 0.7: 아주 강한 상관관계
        - 0.7 ~ 0.3 : 강한 상관관계
        - 0.3 ~ 0.1 : 약한 상관관계
        - 0.1 ~ 0 : 관계없다.
- 상관 계수 계산
    ```python
    df[[계산하고 싶은 컬럼명 리스트]].corr()
    ```

## 3. 막대 그래프 (Bar plot) 그리기
### 막대 그래프 (Bar plot)
- **수량/값의 크기를 막대 형식으로 나타낸 그래프**
- Bar plot을 사용하는 이유
    - 범주형 데이터의 class별 개수를 확인할 때 사용
- 막대그래프: `plt.bar(x, height)`, 수평막대그래프: `plt.barh(y, width)`
    - 1번 인수: 분류값
    - 2번 인수: 개수
- 수평막대그래프의 경우 밑에서부터 막대가 생성된다.

### 설정
- width(height): 막대의 두께

### text()
- 그래프에 text 넣기
- `plt.text(x좌표, y좌표, "출력할 text")`
- 막대그래프의 경우 분류 값의 범위에 따라 x좌표가 0, 1, 2로 설정된다.
- 단점: 값의 위치를 일일히 지정해주어야 함
- 주요 사용 방법
- column 값이 문자일 경우
```python
for x, y in enumerate(df[y]):
    plt.text(x, y, str(y))
```

- column 값이 숫자일 경우
```python
for x, y in zip(df.columns, df[y]):  # column 의 값이 int 일 경우 원래 index 값이랑 다르기 때문에 zip을 사용해야 한다.
    plt.text(x, y, str(y))
```


### ylim()
- 그래프 시작점과 끝점 지정하기
- `plt.ylim(시작값, 끝값)` 또는 `plt.xlim(시작값, 끝값)`
- 막대 그래프가 시작하는 지점과 끝점을 설정할 수 있다.
- 특정 부분의 확실한 변화를 보기 위해 사용


## 4. 파이차트 (Pie chart) 그리기
- **각 범주가 데이터에서 차지하는 비율을 나타낸 그래프**
- Pie chart를 사용하는 이유
    - 각 범주(Category)의 비율을 확인할 때 사용
- `plt.pie(x, labels)` 또는 `axis.pie(x, labels)`
    - x, labels 인수
        - x: 값 (값들을 100을 기준으로 비율을 계산해 크기 설정)
        - label: 값들의 label

- `autopct=None`: 조각내에 표시될 비율의 문자열 형식. '%fmt문자'
    - fmt문자: f(실수), d(정수), %% (%)
- `pctdistance=0.5`: 표시한 문자열 위치 조정
- `shadow=False`: 입체적으로 보일 수 있게 그림자가 생김
- `explode=None`: 내용을 분리하고 싶을 때 사용
    - 사용 예시
        `explode=[0, 0, 0.2, 0, 0]`
- `textprops={}`: text 설정을 선택할 수 있다
    - 'fontsize': 폰트사이즈
    - 'color': 글씨색
    - 'fontweight': 굵기 정도

## 5. 히스토그램(Histogram) 그리기
- **도수분포표를 바탕으로 나타낸 그래프**
    - 도수분포표: 연속형 자료를 특정 구간(bin)으로 나눠 그 빈도를 나타낸 표
        - 빈도 확인이나 **분포**를 볼때 사용한다.
- Histogram을 사용하는 이유
    - 연속형 값을 그래프로 그리기(시각화) 위해 사용
- `plt.hist(data, bins=[계급개수-몇등분인지])`
    - data: 연속형 값들을 원소로 하는 1차원 자료구조


## 6. 상자그래프(Boxplot) 그리기
- **연속형 값들의 사분위수, 극단값들을 이용해 값들의 분포를 나타낸 그래프**
    - 1분위-아랫값, 2분위-중앙값, 3분위-윗값
    - 선의 범위-정상 범위내의 최소값, 최대값
    - 선 범위 밖의 값-정상 범위에서 벗어난 값
    - IQR(Inter Quatile Range)-3분위수 - 1분위수, 중간 50$ 값의 범위
- Boxplot를 사용하는 이유
    - 값들의 **분포**를 확인하기 위해서
