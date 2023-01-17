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
### rugplot
- 각 데이터들의 위치를 보여준다.

- 기본 구문
    ```python
    sns.rugplot(자료구조)
    ```