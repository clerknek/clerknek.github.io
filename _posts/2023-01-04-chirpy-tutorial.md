---
title: '[Chirpy] 5분만에 끝내는 Github Page 만들기'
date: 23-01-04 20:11:11 +0800
categories: ['Github', 'Github Page']
tags: [github, blog, chirpy, jekyll, windows]     # TAG names should always be lowercase
---

> 이번 포스팅에서는 Chirpy Starter를 이용해 간단하게 Github Page 만드는 법을 설명드리겠습니다. 관련 내용은 아래 제작자분 사이트에서 참고하였습니다.
> 아래 내용은 windows 기반으로 했습니다.

> - Chirpy 제작자 Github 주소
> <https://chirpy.cotes.page/posts/getting-started/#option-1-using-the-chirpy-starter>
> - Chirpy 튜토리얼
> <https://chirpy.cotes.page/categories/tutorial/>

## 사전 준비
Github Page를 만들기 위해 우선 [Github 사이트](https://github.com/)에 들어가셔서 회원가입을 하셔야 됩니다.
가입 후 로그인이 끝났다면 Github Page를 만들 준비가 끝났습니다.

## Github Page 만들기
<https://github.com/cotes2020/chirpy-starter/generate>
1. 위 링크로 들어가셔서 아래 사진 ① 부분에 `(자신의 깃허브 닉네임).github.io`를 입력하고 ②에 체크한 후 ③에 있는 버튼을 눌러 repository를 생성합니다.
>![chirpy-tutorial_01_01](/images/githubpage/chirpy-tutorial_01_01.jpg)

2. 새롭게 생성된 repository에 들어가면 이런 파일들이 있는데 그 중 `_config.yml`파일에 들어갑니다.
>![chirpy-tutorial_01_02](/images/githubpage/chirpy-tutorial_01_02.png)

3. Github Page url을 설정해주기 위해 `_config.yml`파일 상단에 위치한 편집 버튼을 누릅니다.
>![chirpy-tutorial_01_03](/images/githubpage/chirpy-tutorial_01_03.png)

4. `yml`파일을 내리다 보면 `url: ''` 부분이 있는 데 그 부분을 `https://(1번에서 생성한 repository 이름)`을 입력한 후 스크롤을 마지막까지 내려 파일을 저장합니다. 
입력 예시) `url: 'https://clerknek.github.io'`
>![chirpy-tutorial_01_04](/images/githubpage/chirpy-tutorial_01_04.png)

5. repository 상단에 위치한 **Actions** 탭에 들어가셔서 **workflow**가 초록색 체크 표시가 뜰 때까지 기다려 줍니다.
>![chirpy-tutorial_01_05](/images/githubpage/chirpy-tutorial_01_05.png)
>![chirpy-tutorial_01_06](/images/githubpage/chirpy-tutorial_01_06.png)

6. **workflow**에서 체크 표시가 뜨면 ① Github 상단에 위치한 **Settings**탭에 들어가신 후 ② Page 탭에 들어가 ③ **Source**를 **Github Actions**로 바꿉니다. 

>![chirpy-tutorial_01_07](/images/githubpage/chirpy-tutorial_01_07.png)

7. 6번을 다 끝내고 6번 사진의 ④ **Visit site** 버튼을 눌러주면 아래와 같이 chirpy 테마가 적용된 여러분의 Github Page를 확인하실 수 있습니다.
>![chirpy-tutorial_01_08](/images/githubpage/chirpy-tutorial_01_08.png)

## 마치며
이번 포스팅에서는 Jekyll에 chirpy 테마를 이용해 간단하게 Github Page를 만들어 보았습니다. 저도 아직 Github Page를 많이 써보지 않았지만 간단하게 그 이후 사용법을 설명 드리자면 다음과 같습니다.
- Page의 기본 텍스트 설정 변경 방법: `_config.yml` 파일을 수정한다.
- 포스팅 글 쓰는 법: Markdown 파일을 `_posts` 폴더에 넣는다.
- Markdown 작성 시 유의할 점
    - Markdown 파일을 만든 후 파일 맨 위에 아래 나와 있는 코드를 입력해 기본 세팅을 해줘야 한다.
    ```
    ---
    title: '[Chirpy] 5분만에 끝내는 Github Page 만들기'
    date: 22-12-19 20:11:11 +0800
    categories: ['Github', 'Github Page']
    tags: [github, blog, chirpy, jekyll, windows]     # TAG names should always be lowercase
    ---
    ```
    - 사진을 추가할 때는 사진의 위치를 파악하고 `[사진 이름](사진 위치)` 형식으로 넣어 주되 사진 위치 맨 앞에는 항상 `/`를 붙여주도록 한다.
    - 파일 제목은 항상 `YY-MM-DD-(간단한 제목).md` 형식으로 적어야 한다. 이때 `(간단한 제목)`은 이후 포스팅 url 안에 들어가게 된다. 
    제목 예시) `2023-01-04-chirpy-tutorial.md`

좀 더 자세한 내용은 위에 올려 두었던 제작자 분의 사이트에서 확인하실 수 있습니다. 
Github Page를 사용해본지 얼마 안되서 간단하게 시작하는 것만 알려드렸습니다. 추후 시간이 나면 다음 포스팅에 사용법에 대해 좀 더 자세히 적어보도록 하겠습니다.

