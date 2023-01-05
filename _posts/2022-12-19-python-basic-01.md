---
title: [Python 기초]01. 인공지능 이해
date: 22-12-19 20:11:11 +0800
categories: [Python, Python 기초]
tags: [python]     # TAG names should always be lowercase
---

# 프로그래밍 개요

## 프로그램(Program)이란
- 컴퓨터에 특정 작업을 실행시키기 위한 처리 방법과 순서를 논리적으로 작성한 명령문들의 집합

## 관련 용어
- 로직(Logic)
    - 프로그램이 시작해서 목적한 결과를 낼 때까지 일의 순서, 논리적인 흐름을 **프로그램 로직**이라 한다.
- 프로그래밍(Programming)
    - 로직을 작성하는 작업
    - 코드를 작성하는 일이므로 코딩이라고도 한다.
    
- 프로그래밍 언어(Programming Language)
    - 프로그램을 작성할 때 사용하는 언어
    - 범용적인 언어: 파이썬, 자바, C언어
    - 특수 목적의 언어: R, SQL
    - https://www.tiobe.com/tiobe-index/

- Library, API
    - 프로그램을 작성하는데 자주 반복적으로 사용되는 코드들을 미리 작성해 제공하는 것을 말한다.
    - 파이썬에서는 패키지라고도 한다.

## 프로그래밍 언어
- 프로그램 작성시 언어
    - 프로그램은 사람이 이해하는 언어로 작성한다.
    - High Level Language 이라고 한다.
    - High Level Language로 코드를 작성한 것을 **Source code** 라고 한다.
- 프로그램 실행시 언어
    - 컴퓨터는 사람의 언어를 이해하거나 저장하지 못한다. 0과 1(on/off)의 **2진 데이터(binary code)의 기계어**를 사용한다.
    - Low Level Language
    - 기계어로 변환된 코드를 **Binary Code**라고 한다.
    ![기계어](/images/ch01_01.png)

### Compile(번역)과 Interprete(통역)
- 사람이 이해하는 High Level Language 로 작성한 프로그램 코드를 실행할 때는 기계가 이해하는 언어인 기계어(Binary code)로 변환해야 한다.  
언어들 마다 변환하는 방식은 다르지만 다음 두가지 방식이 있다.
- **Compiled 방식**
    - **Compiler(컴파일러)**라는 변환프로그램을 이용해 소스 코드를 한번에 변환해 기계어로된 파일을 생성한다.
    - 소스코드가 아닌 변경된 기계어 파일(바이너리 파일)을 실행한다.
    - **장점**
        - 프로그램 실행속도가 빠르다. _ex)미국 사람에게 한글로 쓴 글을 번역해서 줌_
    - **단점**
        - **OS(Platform) 종속적인이다.** 그래서 OS별로 프로그램을 작성해야 한다. _ex)다른 나라 사람들에게는 그 나라에 맞는 번역된 글을 써줘야 한다_

- **Interpreted 방식**
    - 소스코드를 바로 실행한다.
    - **Interpreter(인터프리터)**라는 실행환경(Runtime Environment)이 실행시 명령문단위로 기계어로 변환하여 실행한다.
    - **장점**
        - **OS(Platform) 독립적이다.** 그래서 프로그램을 하나만 구현하면 OS상관없이 실행된다. +_만든 코드는 변하지 않음_
        - 단 각 OS에는 그 환경에 맞는 Interpreter가 설치되어 있어야 한다.
    - **단점**
        - 실행하는 도중 기계어로 변환하기 때문에 **속도가 느리다**
    - **파이썬은 Interpreted 방식의 언어이다.**       
    ![실행방식](/images/ch01_02.png)

# Python(파이썬) 
![python 로고](/images/ch01_python_logo.png)
![귀도반로섬](/images/ch01_03.png)

- 1991년 네덜란드 프로그래머 귀도 판 로섬(Guido van Rossum) 이 만든 프로그래밍 언어.
- 평이한 영어로 이해할 수 있는 코드와, 일상적인 업무에 적용할 수 있고 프로그램 개발시 긴 시간을 필요로 하지 않는 언어를 목표로 개발함.
- **파이썬 3**
    - 2008년 12월 3일에 기존 2.X 버전과 분리하여 하위호환이 안되는 버전으로 발표됨.
    - 2.x와 3.x는 각각 따로 버전업을 하다 파이썬 2 버전은 2020년 1월 이후 지원이 중단되었다.

## 파이썬의 특징
- 구문의 가독성이 좋다.
    - **코드는 작성하는 것 보다 읽는 경우가 많다.** 는 명제 아래 **코딩 스타일의 일관성을 유지하여 가독성을 높이는 것을 중시한다.**
- 유지보수성이 좋다.
    - 파이썬은 배우기 쉽고, 코드를 읽기 쉽기 때문에 유지보수성이 좋다.
- Interpreted 언어이므로 OS 독립적인 프로그램 작성이 가능
- 다른 언어와의 유연한 확장 구조
    - C나 Java 언어로 작성된 함수들을 호출할 수 있다.
- 동적타입(Dynamically typed)
    - 변수의 타입을 고정하지 않기 때문에 하나의 변수에 다른타입의 값을 대입할 수 있다.
    - 프로그램이 커지면 오류를 발생시킬 확률이 커진다. <-> 정적타입
- 방대한 라이브러리
    - 강력한 표준라이브러리 제공(1st party)
    - 잘 갖춰진 생태계
        - 풍부한 라이브러리들을 다양한 집단에서 제공하여(3rd party Library) 개발 생산성이 좋다.
            - cf) 1st party: 파이썬, 2st party: 파이썬으로 프로그램을 만드는 사람들, 3rd party: 1,2를 제외한 모두

> 파이썬에서는 라이브러리를 패키지라고도 표현한다.

## 파이썬으로 할 수있는 것

- 업무 자동화
    - 스크립트
        - 다른 프로그램이나 system을 제어하는 프로그램을 스크립트라고 한다.
        - 파이썬으로 스크립트를 작성하여 컴퓨터로 하는 다양한 작업을 자동화 시킬 수 있다.
- 범용 어플리케이션 프로그램 개발
    - GUI 기반의 독립형 어플리케이션 개발
- 데이터 과학과 머신러닝
    - 최근에 파이썬이 각광 받는 이유
    - numpy, pandas, scikit-learn등 데이터분석과 머신러닝, 딥러닝관련 강렬한 파이썬 라이브러리들이 있다.
- 웹 어플리케이션, Open API
    - Django, Flask, Fast API 와 같은 파이썬 기반 웹 프레임워크를 이용하면 웹 어플리케이션을 빠르고 쉽게 개발 할 수 있다.

### 파이썬으로 할 수 없는 것
- 시스템 프로그래밍(하드웨어 전용 드라이버, 펌웨어등). (C/C++등을 이용)
- 모바일 앱 개발
    - kivy 라이브러리를 이용하면 가능은 하나 아직 활성화 되지 않았다.

# 파이썬 실행환경에 라이브러리 설치

## PyPI (Python Package Index) 이용
- 파이썬 3rd party Library들의 저장소
    - 파이썬의 Library들이 관리되고 있는 라이브러리 중앙 저장소
    - 파이썬은 필요한 라이브러리들을 pip 명령어를 이용해 PyPI에서 다운 받아 설치 하여 사용한다.
    - https://pypi.org/
        - 패키지 검색 사이트
    



```python
pip list
```

    Package                           Version
    --------------------------------- --------------------
    alabaster                         0.7.12
    anaconda-client                   1.11.0
    anaconda-navigator                2.3.1
    anaconda-project                  0.11.1
    anyio                             3.5.0
    appdirs                           1.4.4
    argon2-cffi                       21.3.0
    argon2-cffi-bindings              21.2.0
    arrow                             1.2.2
    astroid                           2.11.7
    astropy                           5.1
    atomicwrites                      1.4.0
    attrs                             21.4.0
    Automat                           20.2.0
    autopep8                          1.6.0
    Babel                             2.9.1
    backcall                          0.2.0
    backports.functools-lru-cache     1.6.4
    backports.tempfile                1.0
    backports.weakref                 1.0.post1
    bcrypt                            3.2.0
    beautifulsoup4                    4.11.1
    binaryornot                       0.4.4
    bitarray                          2.5.1
    bkcharts                          0.2
    black                             22.6.0
    bleach                            4.1.0
    bokeh                             2.4.3
    boto3                             1.24.28
    botocore                          1.27.28
    Bottleneck                        1.3.5
    brotlipy                          0.7.0
    certifi                           2022.9.14
    cffi                              1.15.1
    chardet                           4.0.0
    charset-normalizer                2.0.4
    click                             8.0.4
    cloudpickle                       2.0.0
    clyent                            1.2.2
    colorama                          0.4.5
    colorcet                          3.0.0
    comtypes                          1.1.10
    conda                             22.11.1
    conda-build                       3.22.0
    conda-content-trust               0.1.3
    conda-pack                        0.6.0
    conda-package-handling            1.9.0
    conda-repo-cli                    1.0.24
    conda-token                       0.4.0
    conda-verify                      3.4.2
    constantly                        15.1.0
    cookiecutter                      1.7.3
    cryptography                      37.0.1
    cssselect                         1.1.0
    cycler                            0.11.0
    Cython                            0.29.32
    cytoolz                           0.11.0
    daal4py                           2021.6.0
    dask                              2022.7.0
    datashader                        0.14.1
    datashape                         0.5.4
    debugpy                           1.5.1
    decorator                         5.1.1
    defusedxml                        0.7.1
    diff-match-patch                  20200713
    dill                              0.3.4
    distributed                       2022.7.0
    docutils                          0.18.1
    entrypoints                       0.4
    et-xmlfile                        1.1.0
    fastjsonschema                    2.16.2
    filelock                          3.6.0
    flake8                            4.0.1
    Flask                             1.1.2
    fonttools                         4.25.0
    fsspec                            2022.7.1
    future                            0.18.2
    gensim                            4.1.2
    glob2                             0.7
    greenlet                          1.1.1
    h5py                              3.7.0
    HeapDict                          1.0.1
    holoviews                         1.15.0
    hvplot                            0.8.0
    hyperlink                         21.0.0
    idna                              3.3
    imagecodecs                       2021.8.26
    imageio                           2.19.3
    imagesize                         1.4.1
    importlib-metadata                4.11.3
    incremental                       21.3.0
    inflection                        0.5.1
    iniconfig                         1.1.1
    intake                            0.6.5
    intervaltree                      3.1.0
    ipykernel                         6.15.2
    ipython                           7.31.1
    ipython-genutils                  0.2.0
    ipywidgets                        7.6.5
    isort                             5.9.3
    itemadapter                       0.3.0
    itemloaders                       1.0.4
    itsdangerous                      2.0.1
    jdcal                             1.4.1
    jedi                              0.18.1
    jellyfish                         0.9.0
    Jinja2                            2.11.3
    jinja2-time                       0.2.0
    jmespath                          0.10.0
    joblib                            1.1.0
    json5                             0.9.6
    jsonschema                        4.16.0
    jupyter                           1.0.0
    jupyter_client                    7.3.4
    jupyter-console                   6.4.3
    jupyter-contrib-core              0.4.2
    jupyter-contrib-nbextensions      0.7.0
    jupyter_core                      4.11.1
    jupyter-highlight-selected-word   0.2.0
    jupyter-nbextensions-configurator 0.6.1
    jupyter-server                    1.18.1
    jupyterlab                        3.4.4
    jupyterlab-pygments               0.1.2
    jupyterlab-server                 2.10.3
    jupyterlab-widgets                1.0.0
    keyring                           23.4.0
    kiwisolver                        1.4.2
    lazy-object-proxy                 1.6.0
    libarchive-c                      2.9
    llvmlite                          0.38.0
    locket                            1.0.0
    lxml                              4.9.1
    lz4                               3.1.3
    Markdown                          3.3.4
    MarkupSafe                        2.0.1
    matplotlib                        3.5.2
    matplotlib-inline                 0.1.6
    mccabe                            0.6.1
    menuinst                          1.4.19
    mistune                           0.8.4
    mkl-fft                           1.3.1
    mkl-random                        1.2.2
    mkl-service                       2.4.0
    mock                              4.0.3
    mpmath                            1.2.1
    msgpack                           1.0.3
    multipledispatch                  0.6.0
    munkres                           1.1.4
    mypy-extensions                   0.4.3
    navigator-updater                 0.3.0
    nbclassic                         0.3.5
    nbclient                          0.5.13
    nbconvert                         6.4.4
    nbformat                          5.5.0
    nest-asyncio                      1.5.5
    networkx                          2.8.4
    nltk                              3.7
    nose                              1.3.7
    notebook                          6.4.12
    numba                             0.55.1
    numexpr                           2.8.3
    numpy                             1.21.5
    numpydoc                          1.4.0
    olefile                           0.46
    openpyxl                          3.0.10
    packaging                         21.3
    pandas                            1.4.4
    pandocfilters                     1.5.0
    panel                             0.13.1
    param                             1.12.0
    paramiko                          2.8.1
    parsel                            1.6.0
    parso                             0.8.3
    partd                             1.2.0
    pathlib                           1.0.1
    pathspec                          0.9.0
    patsy                             0.5.2
    pep8                              1.7.1
    pexpect                           4.8.0
    pickleshare                       0.7.5
    Pillow                            9.2.0
    pip                               22.2.2
    pkginfo                           1.8.2
    platformdirs                      2.5.2
    plotly                            5.9.0
    pluggy                            1.0.0
    poyo                              0.5.0
    prometheus-client                 0.14.1
    prompt-toolkit                    3.0.20
    Protego                           0.1.16
    psutil                            5.9.0
    ptyprocess                        0.7.0
    py                                1.11.0
    pyasn1                            0.4.8
    pyasn1-modules                    0.2.8
    pycodestyle                       2.8.0
    pycosat                           0.6.3
    pycparser                         2.21
    pyct                              0.4.8
    pycurl                            7.45.1
    PyDispatcher                      2.0.5
    pydocstyle                        6.1.1
    pyerfa                            2.0.0
    pyflakes                          2.4.0
    Pygments                          2.11.2
    PyHamcrest                        2.0.2
    PyJWT                             2.4.0
    pylint                            2.14.5
    pyls-spyder                       0.4.0
    PyNaCl                            1.5.0
    pyodbc                            4.0.34
    pyOpenSSL                         22.0.0
    pyparsing                         3.0.9
    pyrsistent                        0.18.0
    PySocks                           1.7.1
    pytest                            7.1.2
    python-dateutil                   2.8.2
    python-lsp-black                  1.0.0
    python-lsp-jsonrpc                1.0.0
    python-lsp-server                 1.3.3
    python-slugify                    5.0.2
    python-snappy                     0.6.0
    pytz                              2022.1
    pyviz-comms                       2.0.2
    PyWavelets                        1.3.0
    pywin32                           302
    pywin32-ctypes                    0.2.0
    pywinpty                          2.0.2
    PyYAML                            6.0
    pyzmq                             23.2.0
    QDarkStyle                        3.0.2
    qstylizer                         0.1.10
    QtAwesome                         1.0.3
    qtconsole                         5.2.2
    QtPy                              2.2.0
    queuelib                          1.5.0
    regex                             2022.7.9
    requests                          2.28.1
    requests-file                     1.5.1
    rope                              0.22.0
    Rtree                             0.9.7
    ruamel.yaml                       0.17.21
    ruamel.yaml.clib                  0.2.6
    ruamel-yaml-conda                 0.15.100
    s3transfer                        0.6.0
    scikit-image                      0.19.2
    scikit-learn                      1.0.2
    scikit-learn-intelex              2021.20221004.171935
    scipy                             1.9.1
    Scrapy                            2.6.2
    seaborn                           0.11.2
    Send2Trash                        1.8.0
    service-identity                  18.1.0
    setuptools                        63.4.1
    sip                               4.19.13
    six                               1.16.0
    smart-open                        5.2.1
    sniffio                           1.2.0
    snowballstemmer                   2.2.0
    sortedcollections                 2.1.0
    sortedcontainers                  2.4.0
    soupsieve                         2.3.1
    Sphinx                            5.0.2
    sphinxcontrib-applehelp           1.0.2
    sphinxcontrib-devhelp             1.0.2
    sphinxcontrib-htmlhelp            2.0.0
    sphinxcontrib-jsmath              1.0.1
    sphinxcontrib-qthelp              1.0.3
    sphinxcontrib-serializinghtml     1.1.5
    spyder                            5.2.2
    spyder-kernels                    2.2.1
    SQLAlchemy                        1.4.39
    statsmodels                       0.13.2
    sympy                             1.10.1
    tables                            3.6.1
    tabulate                          0.8.10
    TBB                               0.2
    tblib                             1.7.0
    tenacity                          8.0.1
    terminado                         0.13.1
    testpath                          0.6.0
    text-unidecode                    1.3
    textdistance                      4.2.1
    threadpoolctl                     2.2.0
    three-merge                       0.1.1
    tifffile                          2021.7.2
    tinycss                           0.4
    tldextract                        3.2.0
    toml                              0.10.2
    tomli                             2.0.1
    tomlkit                           0.11.1
    toolz                             0.11.2
    tornado                           6.1
    tqdm                              4.64.1
    traitlets                         5.1.1
    Twisted                           22.2.0
    twisted-iocpsupport               1.0.2
    typing_extensions                 4.3.0
    ujson                             5.4.0
    Unidecode                         1.2.0
    urllib3                           1.26.11
    w3lib                             1.21.0
    watchdog                          2.1.6
    wcwidth                           0.2.5
    webencodings                      0.5.1
    websocket-client                  0.58.0
    Werkzeug                          2.0.3
    wheel                             0.37.1
    widgetsnbextension                3.5.2
    win-inet-pton                     1.1.0
    win-unicode-console               0.5
    wincertstore                      0.2
    wrapt                             1.14.1
    xarray                            0.20.1
    xlrd                              2.0.1
    XlsxWriter                        3.0.3
    xlwings                           0.27.15
    yapf                              0.31.0
    zict                              2.1.0
    zipp                              3.8.0
    zope.interface                    5.4.0
    Note: you may need to restart the kernel to use updated packages.
    


```python
pip show pandas
```

    Name: pandas
    Version: 1.4.4
    Summary: Powerful data structures for data analysis, time series, and statistics
    Home-page: https://pandas.pydata.org
    Author: The Pandas Development Team
    Author-email: pandas-dev@python.org
    License: BSD-3-Clause
    Location: c:\users\jeonj\anaconda3\lib\site-packages
    Requires: numpy, python-dateutil, pytz
    Required-by: datashader, holoviews, hvplot, seaborn, statsmodels, xarray
    Note: you may need to restart the kernel to use updated packages.
    

## Conda package repository 이용
- 아나콘다에서 관리하는 패키지 저장소
- https://anaconda.org/anaconda/repo
    - 패키지 검색 사이트
    
    ![image-3.png](attachment:image-3.png)


```python
conda list
```

    # packages in environment at C:\Users\jeonj\anaconda3:
    #
    # Name                    Version                   Build  Channel
    _ipyw_jlab_nb_ext_conf    0.1.0            py39haa95532_0  
    alabaster                 0.7.12             pyhd3eb1b0_0  
    anaconda                  2022.10                  py39_0  
    anaconda-client           1.11.0           py39haa95532_0  
    anaconda-navigator        2.3.1            py39haa95532_0  
    anaconda-project          0.11.1           py39haa95532_0  
    anyio                     3.5.0            py39haa95532_0  
    appdirs                   1.4.4              pyhd3eb1b0_0  
    argon2-cffi               21.3.0             pyhd3eb1b0_0  
    argon2-cffi-bindings      21.2.0           py39h2bbff1b_0  
    arrow                     1.2.2              pyhd3eb1b0_0  
    astroid                   2.11.7           py39haa95532_0  
    astropy                   5.1              py39h080aedc_0  
    atomicwrites              1.4.0                      py_0  
    attrs                     21.4.0             pyhd3eb1b0_0  
    automat                   20.2.0                     py_0  
    autopep8                  1.6.0              pyhd3eb1b0_1  
    babel                     2.9.1              pyhd3eb1b0_0  
    backcall                  0.2.0              pyhd3eb1b0_0  
    backports                 1.1                pyhd3eb1b0_0  
    backports.functools_lru_cache 1.6.4              pyhd3eb1b0_0  
    backports.tempfile        1.0                pyhd3eb1b0_1  
    backports.weakref         1.0.post1                  py_1  
    bcrypt                    3.2.0            py39h2bbff1b_1  
    beautifulsoup4            4.11.1           py39haa95532_0  
    binaryornot               0.4.4              pyhd3eb1b0_1  
    bitarray                  2.5.1            py39h2bbff1b_0  
    bkcharts                  0.2              py39haa95532_1  
    black                     22.6.0           py39haa95532_0  
    blas                      1.0                         mkl  
    bleach                    4.1.0              pyhd3eb1b0_0  
    blosc                     1.21.0               h19a0ad4_1  
    bokeh                     2.4.3            py39haa95532_0  
    boto3                     1.24.28          py39haa95532_0  
    botocore                  1.27.28          py39haa95532_0  
    bottleneck                1.3.5            py39h080aedc_0  
    brotli                    1.0.9                h2bbff1b_7  
    brotli-bin                1.0.9                h2bbff1b_7  
    brotlipy                  0.7.0           py39h2bbff1b_1003  
    bzip2                     1.0.8                he774522_0  
    ca-certificates           2022.07.19           haa95532_0  
    certifi                   2022.9.14        py39haa95532_0  
    cffi                      1.15.1           py39h2bbff1b_0  
    cfitsio                   3.470                h2bbff1b_7  
    chardet                   4.0.0           py39haa95532_1003  
    charls                    2.2.0                h6c2663c_0  
    charset-normalizer        2.0.4              pyhd3eb1b0_0  
    click                     8.0.4            py39haa95532_0  
    cloudpickle               2.0.0              pyhd3eb1b0_0  
    clyent                    1.2.2            py39haa95532_1  
    colorama                  0.4.5            py39haa95532_0  
    colorcet                  3.0.0            py39haa95532_0  
    comtypes                  1.1.10          py39haa95532_1002  
    conda                     22.11.1          py39haa95532_4  
    conda-build               3.22.0           py39haa95532_0  
    conda-content-trust       0.1.3            py39haa95532_0  
    conda-env                 2.6.0                haa95532_1  
    conda-pack                0.6.0              pyhd3eb1b0_0  
    conda-package-handling    1.9.0            py39h8cc25b3_1  
    conda-repo-cli            1.0.24           py39haa95532_0  
    conda-token               0.4.0              pyhd3eb1b0_0  
    conda-verify              3.4.2                      py_1  
    console_shortcut          0.1.1                         4  
    constantly                15.1.0             pyh2b92418_0  
    cookiecutter              1.7.3              pyhd3eb1b0_0  
    cryptography              37.0.1           py39h21b164f_0  
    cssselect                 1.1.0              pyhd3eb1b0_0  
    curl                      7.84.0               h2bbff1b_0  
    cycler                    0.11.0             pyhd3eb1b0_0  
    cython                    0.29.32          py39hd77b12b_0  
    cytoolz                   0.11.0           py39h2bbff1b_0  
    daal4py                   2021.6.0         py39h757b272_1  
    dal                       2021.6.0           h59b6b97_874  
    dask                      2022.7.0         py39haa95532_0  
    dask-core                 2022.7.0         py39haa95532_0  
    dataclasses               0.8                pyh6d0b6a4_7  
    datashader                0.14.1           py39haa95532_0  
    datashape                 0.5.4            py39haa95532_1  
    debugpy                   1.5.1            py39hd77b12b_0  
    decorator                 5.1.1              pyhd3eb1b0_0  
    defusedxml                0.7.1              pyhd3eb1b0_0  
    diff-match-patch          20200713           pyhd3eb1b0_0  
    dill                      0.3.4              pyhd3eb1b0_0  
    distributed               2022.7.0         py39haa95532_0  
    docutils                  0.18.1           py39haa95532_3  
    entrypoints               0.4              py39haa95532_0  
    et_xmlfile                1.1.0            py39haa95532_0  
    fftw                      3.3.9                h2bbff1b_1  
    filelock                  3.6.0              pyhd3eb1b0_0  
    flake8                    4.0.1              pyhd3eb1b0_1  
    flask                     1.1.2              pyhd3eb1b0_0  
    fonttools                 4.25.0             pyhd3eb1b0_0  
    freetype                  2.10.4               hd328e21_0  
    fsspec                    2022.7.1         py39haa95532_0  
    future                    0.18.2           py39haa95532_1  
    gensim                    4.1.2            py39hd77b12b_0  
    giflib                    5.2.1                h62dcd97_0  
    glob2                     0.7                pyhd3eb1b0_0  
    greenlet                  1.1.1            py39hd77b12b_0  
    h5py                      3.7.0            py39h3de5c98_0  
    hdf5                      1.10.6               h1756f20_1  
    heapdict                  1.0.1              pyhd3eb1b0_0  
    holoviews                 1.15.0           py39haa95532_0  
    hvplot                    0.8.0            py39haa95532_0  
    hyperlink                 21.0.0             pyhd3eb1b0_0  
    icc_rt                    2022.1.0             h6049295_2  
    icu                       58.2                 ha925a31_3  
    idna                      3.3                pyhd3eb1b0_0  
    imagecodecs               2021.8.26        py39hc0a7faf_1  
    imageio                   2.19.3           py39haa95532_0  
    imagesize                 1.4.1            py39haa95532_0  
    importlib-metadata        4.11.3           py39haa95532_0  
    importlib_metadata        4.11.3               hd3eb1b0_0  
    incremental               21.3.0             pyhd3eb1b0_0  
    inflection                0.5.1            py39haa95532_0  
    iniconfig                 1.1.1              pyhd3eb1b0_0  
    intake                    0.6.5              pyhd3eb1b0_0  
    intel-openmp              2021.4.0          haa95532_3556  
    intervaltree              3.1.0              pyhd3eb1b0_0  
    ipykernel                 6.15.2           py39haa95532_0  
    ipython                   7.31.1           py39haa95532_1  
    ipython_genutils          0.2.0              pyhd3eb1b0_1  
    ipywidgets                7.6.5              pyhd3eb1b0_1  
    isort                     5.9.3              pyhd3eb1b0_0  
    itemadapter               0.3.0              pyhd3eb1b0_0  
    itemloaders               1.0.4              pyhd3eb1b0_1  
    itsdangerous              2.0.1              pyhd3eb1b0_0  
    jdcal                     1.4.1              pyhd3eb1b0_0  
    jedi                      0.18.1           py39haa95532_1  
    jellyfish                 0.9.0            py39h2bbff1b_0  
    jinja2                    2.11.3             pyhd3eb1b0_0  
    jinja2-time               0.2.0              pyhd3eb1b0_3  
    jmespath                  0.10.0             pyhd3eb1b0_0  
    joblib                    1.1.0              pyhd3eb1b0_0  
    jpeg                      9e                   h2bbff1b_0  
    jq                        1.6                  haa95532_1  
    json5                     0.9.6              pyhd3eb1b0_0  
    jsonschema                4.16.0           py39haa95532_0  
    jupyter                   1.0.0            py39haa95532_8  
    jupyter-contrib-core      0.4.2                    pypi_0    pypi
    jupyter-contrib-nbextensions 0.7.0                    pypi_0    pypi
    jupyter-highlight-selected-word 0.2.0                    pypi_0    pypi
    jupyter-nbextensions-configurator 0.6.1                    pypi_0    pypi
    jupyter_client            7.3.4            py39haa95532_0  
    jupyter_console           6.4.3              pyhd3eb1b0_0  
    jupyter_core              4.11.1           py39haa95532_0  
    jupyter_server            1.18.1           py39haa95532_0  
    jupyterlab                3.4.4            py39haa95532_0  
    jupyterlab_pygments       0.1.2                      py_0  
    jupyterlab_server         2.10.3             pyhd3eb1b0_1  
    jupyterlab_widgets        1.0.0              pyhd3eb1b0_1  
    keyring                   23.4.0           py39haa95532_0  
    kiwisolver                1.4.2            py39hd77b12b_0  
    lazy-object-proxy         1.6.0            py39h2bbff1b_0  
    lcms2                     2.12                 h83e58a3_0  
    lerc                      3.0                  hd77b12b_0  
    libaec                    1.0.4                h33f27b4_1  
    libarchive                3.6.1                hebabd0d_0  
    libbrotlicommon           1.0.9                h2bbff1b_7  
    libbrotlidec              1.0.9                h2bbff1b_7  
    libbrotlienc              1.0.9                h2bbff1b_7  
    libcurl                   7.84.0               h86230a5_0  
    libdeflate                1.8                  h2bbff1b_5  
    libiconv                  1.16                 h2bbff1b_2  
    liblief                   0.11.5               hd77b12b_1  
    libpng                    1.6.37               h2a8f88b_0  
    libsodium                 1.0.18               h62dcd97_0  
    libspatialindex           1.9.3                h6c2663c_0  
    libssh2                   1.10.0               hcd4344a_0  
    libtiff                   4.4.0                h8a3f274_0  
    libwebp                   1.2.2                h2bbff1b_0  
    libxml2                   2.9.14               h0ad7f3c_0  
    libxslt                   1.1.35               h2bbff1b_0  
    libzopfli                 1.0.3                ha925a31_0  
    llvmlite                  0.38.0           py39h23ce68f_0  
    locket                    1.0.0            py39haa95532_0  
    lxml                      4.9.1            py39h1985fb9_0  
    lz4                       3.1.3            py39h2bbff1b_0  
    lz4-c                     1.9.3                h2bbff1b_1  
    lzo                       2.10                 he774522_2  
    m2-msys2-runtime          2.5.0.17080.65c939c               3  
    m2-patch                  2.7.5                         2  
    m2w64-libwinpthread-git   5.0.0.4634.697f757               2  
    markdown                  3.3.4            py39haa95532_0  
    markupsafe                2.0.1            py39h2bbff1b_0  
    matplotlib                3.5.2            py39haa95532_0  
    matplotlib-base           3.5.2            py39hd77b12b_0  
    matplotlib-inline         0.1.6            py39haa95532_0  
    mccabe                    0.6.1            py39haa95532_2  
    menuinst                  1.4.19           py39h59b6b97_0  
    mistune                   0.8.4           py39h2bbff1b_1000  
    mkl                       2021.4.0           haa95532_640  
    mkl-service               2.4.0            py39h2bbff1b_0  
    mkl_fft                   1.3.1            py39h277e83a_0  
    mkl_random                1.2.2            py39hf11a4ad_0  
    mock                      4.0.3              pyhd3eb1b0_0  
    mpmath                    1.2.1            py39haa95532_0  
    msgpack-python            1.0.3            py39h59b6b97_0  
    msys2-conda-epoch         20160418                      1  
    multipledispatch          0.6.0            py39haa95532_0  
    munkres                   1.1.4                      py_0  
    mypy_extensions           0.4.3            py39haa95532_1  
    navigator-updater         0.3.0            py39haa95532_0  
    nbclassic                 0.3.5              pyhd3eb1b0_0  
    nbclient                  0.5.13           py39haa95532_0  
    nbconvert                 6.4.4            py39haa95532_0  
    nbformat                  5.5.0            py39haa95532_0  
    nest-asyncio              1.5.5            py39haa95532_0  
    networkx                  2.8.4            py39haa95532_0  
    nltk                      3.7                pyhd3eb1b0_0  
    nose                      1.3.7           pyhd3eb1b0_1008  
    notebook                  6.4.12           py39haa95532_0  
    numba                     0.55.1           py39hf11a4ad_0  
    numexpr                   2.8.3            py39hb80d3ca_0  
    numpy                     1.21.5           py39h7a0a035_3  
    numpy-base                1.21.5           py39hca35cd5_3  
    numpydoc                  1.4.0            py39haa95532_0  
    olefile                   0.46               pyhd3eb1b0_0  
    openjpeg                  2.4.0                h4fc8c34_0  
    openpyxl                  3.0.10           py39h2bbff1b_0  
    openssl                   1.1.1q               h2bbff1b_0  
    packaging                 21.3               pyhd3eb1b0_0  
    pandas                    1.4.4            py39hd77b12b_0  
    pandocfilters             1.5.0              pyhd3eb1b0_0  
    panel                     0.13.1           py39haa95532_0  
    param                     1.12.0             pyhd3eb1b0_0  
    paramiko                  2.8.1              pyhd3eb1b0_0  
    parsel                    1.6.0            py39haa95532_0  
    parso                     0.8.3              pyhd3eb1b0_0  
    partd                     1.2.0              pyhd3eb1b0_1  
    pathlib                   1.0.1              pyhd3eb1b0_1  
    pathspec                  0.9.0            py39haa95532_0  
    patsy                     0.5.2            py39haa95532_1  
    pep8                      1.7.1            py39haa95532_1  
    pexpect                   4.8.0              pyhd3eb1b0_3  
    pickleshare               0.7.5           pyhd3eb1b0_1003  
    pillow                    9.2.0            py39hdc2b20a_1  
    pip                       22.2.2           py39haa95532_0  
    pkginfo                   1.8.2              pyhd3eb1b0_0  
    platformdirs              2.5.2            py39haa95532_0  
    plotly                    5.9.0            py39haa95532_0  
    pluggy                    1.0.0            py39haa95532_1  
    powershell_shortcut       0.0.1                         3  
    poyo                      0.5.0              pyhd3eb1b0_0  
    prometheus_client         0.14.1           py39haa95532_0  
    prompt-toolkit            3.0.20             pyhd3eb1b0_0  
    prompt_toolkit            3.0.20               hd3eb1b0_0  
    protego                   0.1.16                     py_0  
    psutil                    5.9.0            py39h2bbff1b_0  
    ptyprocess                0.7.0              pyhd3eb1b0_2  
    py                        1.11.0             pyhd3eb1b0_0  
    py-lief                   0.11.5           py39hd77b12b_1  
    pyasn1                    0.4.8              pyhd3eb1b0_0  
    pyasn1-modules            0.2.8                      py_0  
    pycodestyle               2.8.0              pyhd3eb1b0_0  
    pycosat                   0.6.3            py39h2bbff1b_0  
    pycparser                 2.21               pyhd3eb1b0_0  
    pyct                      0.4.8            py39haa95532_1  
    pycurl                    7.45.1           py39hcd4344a_0  
    pydispatcher              2.0.5            py39haa95532_2  
    pydocstyle                6.1.1              pyhd3eb1b0_0  
    pyerfa                    2.0.0            py39h2bbff1b_0  
    pyflakes                  2.4.0              pyhd3eb1b0_0  
    pygments                  2.11.2             pyhd3eb1b0_0  
    pyhamcrest                2.0.2              pyhd3eb1b0_2  
    pyjwt                     2.4.0            py39haa95532_0  
    pylint                    2.14.5           py39haa95532_0  
    pyls-spyder               0.4.0              pyhd3eb1b0_0  
    pynacl                    1.5.0            py39h8cc25b3_0  
    pyodbc                    4.0.34           py39hd77b12b_0  
    pyopenssl                 22.0.0             pyhd3eb1b0_0  
    pyparsing                 3.0.9            py39haa95532_0  
    pyqt                      5.9.2            py39hd77b12b_6  
    pyrsistent                0.18.0           py39h196d8e1_0  
    pysocks                   1.7.1            py39haa95532_0  
    pytables                  3.6.1            py39h56d22b6_1  
    pytest                    7.1.2            py39haa95532_0  
    python                    3.9.13               h6244533_1  
    python-dateutil           2.8.2              pyhd3eb1b0_0  
    python-fastjsonschema     2.16.2           py39haa95532_0  
    python-libarchive-c       2.9                pyhd3eb1b0_1  
    python-lsp-black          1.0.0              pyhd3eb1b0_0  
    python-lsp-jsonrpc        1.0.0              pyhd3eb1b0_0  
    python-lsp-server         1.3.3              pyhd3eb1b0_0  
    python-slugify            5.0.2              pyhd3eb1b0_0  
    python-snappy             0.6.0            py39hd77b12b_3  
    pytz                      2022.1           py39haa95532_0  
    pyviz_comms               2.0.2              pyhd3eb1b0_0  
    pywavelets                1.3.0            py39h2bbff1b_0  
    pywin32                   302              py39h2bbff1b_2  
    pywin32-ctypes            0.2.0           py39haa95532_1000  
    pywinpty                  2.0.2            py39h5da7b33_0  
    pyyaml                    6.0              py39h2bbff1b_1  
    pyzmq                     23.2.0           py39hd77b12b_0  
    qdarkstyle                3.0.2              pyhd3eb1b0_0  
    qstylizer                 0.1.10             pyhd3eb1b0_0  
    qt                        5.9.7            vc14h73c81de_0  
    qtawesome                 1.0.3              pyhd3eb1b0_0  
    qtconsole                 5.2.2              pyhd3eb1b0_0  
    qtpy                      2.2.0            py39haa95532_0  
    queuelib                  1.5.0            py39haa95532_0  
    regex                     2022.7.9         py39h2bbff1b_0  
    requests                  2.28.1           py39haa95532_0  
    requests-file             1.5.1              pyhd3eb1b0_0  
    rope                      0.22.0             pyhd3eb1b0_0  
    rtree                     0.9.7            py39h2eaa2aa_1  
    ruamel.yaml               0.17.21          py39h2bbff1b_0  
    ruamel.yaml.clib          0.2.6            py39h2bbff1b_1  
    ruamel_yaml               0.15.100         py39h2bbff1b_0  
    s3transfer                0.6.0            py39haa95532_0  
    scikit-image              0.19.2           py39hf11a4ad_0  
    scikit-learn              1.0.2            py39hf11a4ad_1  
    scikit-learn-intelex      2021.6.0         py39haa95532_0  
    scipy                     1.9.1            py39he11b74f_0  
    scrapy                    2.6.2            py39haa95532_0  
    seaborn                   0.11.2             pyhd3eb1b0_0  
    send2trash                1.8.0              pyhd3eb1b0_1  
    service_identity          18.1.0             pyhd3eb1b0_1  
    setuptools                63.4.1           py39haa95532_0  
    sip                       4.19.13          py39hd77b12b_0  
    six                       1.16.0             pyhd3eb1b0_1  
    smart_open                5.2.1            py39haa95532_0  
    snappy                    1.1.9                h6c2663c_0  
    sniffio                   1.2.0            py39haa95532_1  
    snowballstemmer           2.2.0              pyhd3eb1b0_0  
    sortedcollections         2.1.0              pyhd3eb1b0_0  
    sortedcontainers          2.4.0              pyhd3eb1b0_0  
    soupsieve                 2.3.1              pyhd3eb1b0_0  
    sphinx                    5.0.2            py39haa95532_0  
    sphinxcontrib-applehelp   1.0.2              pyhd3eb1b0_0  
    sphinxcontrib-devhelp     1.0.2              pyhd3eb1b0_0  
    sphinxcontrib-htmlhelp    2.0.0              pyhd3eb1b0_0  
    sphinxcontrib-jsmath      1.0.1              pyhd3eb1b0_0  
    sphinxcontrib-qthelp      1.0.3              pyhd3eb1b0_0  
    sphinxcontrib-serializinghtml 1.1.5              pyhd3eb1b0_0  
    spyder                    5.2.2            py39haa95532_1  
    spyder-kernels            2.2.1            py39haa95532_0  
    sqlalchemy                1.4.39           py39h2bbff1b_0  
    sqlite                    3.39.3               h2bbff1b_0  
    statsmodels               0.13.2           py39h2bbff1b_0  
    sympy                     1.10.1           py39haa95532_0  
    tabulate                  0.8.10           py39haa95532_0  
    tbb                       2021.6.0             h59b6b97_0  
    tbb4py                    2021.6.0         py39h59b6b97_0  
    tblib                     1.7.0              pyhd3eb1b0_0  
    tenacity                  8.0.1            py39haa95532_1  
    terminado                 0.13.1           py39haa95532_0  
    testpath                  0.6.0            py39haa95532_0  
    text-unidecode            1.3                pyhd3eb1b0_0  
    textdistance              4.2.1              pyhd3eb1b0_0  
    threadpoolctl             2.2.0              pyh0d69192_0  
    three-merge               0.1.1              pyhd3eb1b0_0  
    tifffile                  2021.7.2           pyhd3eb1b0_2  
    tinycss                   0.4             pyhd3eb1b0_1002  
    tk                        8.6.12               h2bbff1b_0  
    tldextract                3.2.0              pyhd3eb1b0_0  
    toml                      0.10.2             pyhd3eb1b0_0  
    tomli                     2.0.1            py39haa95532_0  
    tomlkit                   0.11.1           py39haa95532_0  
    toolz                     0.11.2             pyhd3eb1b0_0  
    tornado                   6.1              py39h2bbff1b_0  
    tqdm                      4.64.1           py39haa95532_0  
    traitlets                 5.1.1              pyhd3eb1b0_0  
    twisted                   22.2.0           py39h2bbff1b_1  
    twisted-iocpsupport       1.0.2            py39h2bbff1b_0  
    typing-extensions         4.3.0            py39haa95532_0  
    typing_extensions         4.3.0            py39haa95532_0  
    tzdata                    2022c                h04d1e81_0  
    ujson                     5.4.0            py39hd77b12b_0  
    unidecode                 1.2.0              pyhd3eb1b0_0  
    urllib3                   1.26.11          py39haa95532_0  
    vc                        14.2                 h21ff451_1  
    vs2015_runtime            14.27.29016          h5e58377_2  
    w3lib                     1.21.0             pyhd3eb1b0_0  
    watchdog                  2.1.6            py39haa95532_0  
    wcwidth                   0.2.5              pyhd3eb1b0_0  
    webencodings              0.5.1            py39haa95532_1  
    websocket-client          0.58.0           py39haa95532_4  
    werkzeug                  2.0.3              pyhd3eb1b0_0  
    wheel                     0.37.1             pyhd3eb1b0_0  
    widgetsnbextension        3.5.2            py39haa95532_0  
    win_inet_pton             1.1.0            py39haa95532_0  
    win_unicode_console       0.5              py39haa95532_0  
    wincertstore              0.2              py39haa95532_2  
    winpty                    0.4.3                         4  
    wrapt                     1.14.1           py39h2bbff1b_0  
    xarray                    0.20.1             pyhd3eb1b0_1  
    xlrd                      2.0.1              pyhd3eb1b0_0  
    xlsxwriter                3.0.3              pyhd3eb1b0_0  
    xlwings                   0.27.15          py39haa95532_0  
    xz                        5.2.6                h8cc25b3_0  
    yaml                      0.2.5                he774522_0  
    yapf                      0.31.0             pyhd3eb1b0_0  
    zeromq                    4.3.4                hd77b12b_0  
    zfp                       0.5.5                hd77b12b_6  
    zict                      2.1.0            py39haa95532_0  
    zipp                      3.8.0            py39haa95532_0  
    zlib                      1.2.12               h8cc25b3_3  
    zope                      1.0              py39haa95532_1  
    zope.interface            5.4.0            py39h2bbff1b_0  
    zstd                      1.5.2                h19a0ad4_0  
    
    Note: you may need to restart the kernel to use updated packages.
    
