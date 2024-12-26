---
title: 옵시디언 노트를 github pages에 게시하기
tags:
  - github
  - obsidian
  - blog
---
![[logo.png]]
## 개요
> [!note]
> 이 문서는  옵시디언 노트를 Github Pages에 게시하여, 무료로 게시하는 내용을 다루고 있습니다.

안녕하세요! 구르미입니다. 현재 저는 이전 [블로그](https://gurumee92.tistory.com/)를 떠나 새로운 마음으로 개발 블로그를 만들고 있습니다. 

왜 블로그 이전을 하느냐.. 여러 가지 이유가 있지만 어느샌가 회사 일에 치이게 되면서부터 자연스레 블로그를 놓게 되었기 때문입니다. 회사 일 정리하기도 바쁜데 블로깅하는건 정말 어렵더라구요. 그래서 근 2년 정도는 노트 앱에다 그 날 얻은 지식을 정리하는 수준으로 적어두었던 것 같습니다.

그러던 중, 노트 앱 "[옵시디언](https://obsidian.md/)"을 Github Pages에 게시하는 [글](https://dev.to/defenderofbasic/host-your-obsidian-notebook-on-github-pages-for-free-8l1)을 보았고, 이거면 제 지식을 간단하게 정리하면서 블로깅을 지속적으로 쉽게 할 수 있겠다란 생각이 들었습니다. 

저처럼, 옵시디언을 이용하면서, 쉽게 블로그 글을 게시하길 원하시는 분들에게 **"옵시디언 노트를 블로그로 만들기"** 시리즈를 만들었습니다. 이번 포스팅은 시리즈의 첫 번째 **"옵시디언 노트를 Github Pages에 게시하기"입니다.

이 포스팅을 마치고 나면 다음을 할 수 있습니다.

* 옵시디언 볼트를 Github 레포와 연동하여 어디서든 블로깅할 수 있는 환경 구축
* 몇 가지 간단한 작업을 통해 옵시디언 노트를 게시
## 템플릿 포크하기
> [!danger]
> 이 절을 진행하기 전, 반드시 [Github](https://github.com/)에 회원가입이 되어 있어야 합니다. 회원가입이 되어 있지 않았다면, 회원가입부터 진행해주세요!

이 문서에서는 DEV 커뮤니티에서 제공하는 템플릿 [레포](https://github.com/DefenderOfBasic/obsidian-quartz-template)를 포크합니다. https://github.com/DefenderOfBasic/obsidian-quartz-template 로 이동한 후 상단의 "fork"를 클릭합니다.
![[1-1.png]]

이제 레포 이름을 입력합니다. 깃헙 블로그 이름의 관례는 `<Github ID>.github.io`입니다. 예를 들어 저 같은 경우는 `gurumee92.github.io`입니다.
![[1-2.png]]

그러면 다음과 같이 개인 레포가 생성될 것입니다
![[1-3.png]]

## Github Actions 활성화하여 페이지 게시 자동화
그 다음 할 일은 `Github Actions`을 활성화하여 페이지를 게시하는 작업을 자동화하는 것입니다. 포크한 본인 레포로 이동한 후, 상단의 "Settings" 메뉴를 클립합니다.
![[1-4.png]]

그 후 좌측 사이드 바에서 "Pages"를 클릭합니다.
![[1-5.png]]

이제 "Build and deployment" 하단에 "Source" 드랍 다운 메뉴에서 "Github Actions"를 선택합니다.
![[1-6.png]]

그러면 페이지 게시하는 것이 자동화된 것입니다. 이 자동화 작업의 결과물은 추후 마지막 절인 "포스팅하기"에서 확인할 수 있습니다.

> [!info]
> 만약 자동화 작업을 본인에게 맞게 커스텀하려면 본인 레포에서 `.github/workflow` 를 확인하세요. 
> ![[1-7.png]]
> 
> 참고: [Github Actions 설명서](https://docs.github.com/ko/actions)
## 옵시디언 볼트 지정하기

## 플러그인 설치하기
## 포스팅하기
## 참고
* [Host your Obsidian notebook on GitHub Pages for free - DEV Community](https://dev.to/defenderofbasic/host-your-obsidian-notebook-on-github-pages-for-free-8l1)
