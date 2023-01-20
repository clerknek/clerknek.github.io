---
title: '[Machine Learning] 02. Numpy 활용'
date: 23-01-20 09:15:23 +0800
categories: ['Data Analysis', '04. Machine Learning']
tags: [python, numpy, machinelearning]     # TAG names should always be lowercase
---

## 배열 인덱싱(Indexing)
- index
    - 원소의 배열 내 식별 번호
    - 0부터 시작
- indexing
    - index를 이용해 원소 조회
- 구문
    - `ndarray[index]`
    - 양수는 index값으로, 음수는 뒤부터 조회 (`[-1] == 마지막 index`)
        
    - N차원 배열
        - `arr[0축 index, 1축 index, 2축 index ... n축 index]`
        - 파이썬 리스트와 차이점
            - 리스트의 경우
            - `py_list[0축 index][1축 index][2축 index]...[n축 index]`

- fancy indexing(팬시 인덱싱)
    - **여러개의 원소를 한번에 조회**할 경우 리스트에 담아 전달
    - 다차원 배열의 경우 각 축별로 list로 지정
    - `arr[[1,2,3,4,5]]`
        - 1차원 배열(vector): 1,2,3,4,5 번 index의 원소들 한번에 조회
    - `arr[[0,3], [1,4]]`
        - [0,3] - 1번축 index list, [1,4] - 2번축 index list
2차원 배열(matrix): [0,1], [3,4] 의 원소들 조회
        - 코드 예시
            ```python
            a = np.arange(30).reshape(5, 6)
            print(a[[0, 3], [1, 4]])
            ```

            
            
            
                [ 1 22]
            
        
        - 좌표 형식이라고 생각하면 편함 위 코드의 경우는 엄밀히 말하면 `a[0, 1]`과 `a[3, 4]`를 조회하는 거
