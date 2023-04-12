---
title: '[Mac] 개발도구 설치'
date: 23-04-01 09:33:36 +0800
categories: ['개발 툴', 'Mac']
tags: [mac, jupyter, eclipse, ]     # TAG names should always be lowercase
---

## &#10052; Jupyter notebook
1. <https://github.com/conda-forge/miniforge>에서 `arm64 (Apple Silicon)` 설치
2. 터미널 실행후 아래 코드 입력
    ```null
    chmod +x ~/Downloads/Miniforge3-MacOSX-arm64.sh

    sh ~/Downloads/Miniforge3-MacOSX-arm64.sh

    source ~/miniforge3/bin/activate
    ```
3. conda (base)에 들어온 거를 확인
    ```null
    (base) username ~ %
    ```
4. pip install 설치 및 설치 확인
    ```null
    curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py

    python3 get-pip.py

    pip3
    ```
5. jupyter 설치
    ```null
    pip install jupyter notebook
    ```
6. `jupyter notebook`실행
    ```null
    jupyter notebook
    ```

> - 참조: <https://velog.io/@pcj1541/1.-Macbook-M1-Tensorflow-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0for-jupyter-notebook>

## &#10052; Eclipse 설치
### JDK
- <https://www.oracle.com/java/technologies/downloads/#jdk17-mac>에 접속
- **Java 17**`Arm 64 DMG Installer`를 설치

### Eclipse IDE
- Eclipse는 자바의 통합 개발 환경(IDE) 중 하나이다.
	- IDE(Integrated Development Environment): 개발의 위한 편의기능을 제공하는 프로그램
- <https://www.eclipse.org>에 접속
- `Download x86_64`를 설치

## &#10052; MySQL
1. MySQL 커뮤니티 버전 설치
	- <https://dev.mysql.com/downloads/mysql/>
	- `macOS xx (ARM, 64-bit), DMG Archive`
2. `.pkg` 파일 실행
3. Configuration 까지 이동
4. Configuration에서 `root` 비밀번호 설정하기 &rarr; 	자신이 기억하기 쉬운걸로
5. MySQL WorkBench 설치
	- <https://downloads.mysql.com/archives/workbench>
	- `macOS (ARM, 64-bit), DMG Archive`
6. 완료

### mac에서 서버 열고 닫기
- 시스템 설정 > 맨 밑에 `MySQL` > `Stop/Start MySQL server` 버튼으로 조종
	- 주로 에러가 날때 한번씩 닫고 열어주면 해결될 때가 많다.

> ### 참조
> - <https://code-algo.tistory.com/29>
> - <https://velog.io/@sorzzzzy/MySQL-Mac-M1-%ED%99%98%EA%B2%BD%EC%97%90%EC%84%9CWorkBench-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0>