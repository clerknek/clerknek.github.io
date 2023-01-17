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

- <https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html>


