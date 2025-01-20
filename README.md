## :dolphin: `github-blog`

:smile: **블로그 바로 가기**
[`https://kdm777.github.io/`](https://kdm777.github.io/)

> 🌴 **목차**

┌ `Deep Learning`  
├ `Computer vision`  
├ `GNN`  
├ `Algorithm`  
├ `Git`  
└ `Project`  

### ▪ 댓글 기능 (utterances 사용)

utterances 관련해서 구글링 해보고 진행하기를 추천.  
기본적인 세팅 방법을 설명하자면,

1. 본인 GitHub에 utterances용 repository 생성
2. [https://github.com/apps/utterances](https://github.com/apps/utterances)에 접속하여 생성한 repo 선택 후 install
3. `_config.yml` 파일 변경 (theme 변경 시에만)

```yml
comments:
  provider: "utterances"
  utterances:
    theme: "github-light" # "github-dark"
    issue_term: "pathname" # pathname은 post의 markdown 파일 이름으로 연결됨
```

4. `_includes/comments-providers/utterances.html` 파일 작성

```yml
# 본인 깃허브 아이디와 생성한 레파지토리 입력
script.setAttribute('repo', 'github-account/repository-name');
# 선택한 깃허브 테마 입력
script.setAttribute('theme', '{{ site.comments.utterances.theme | default: "github-light" }}');
```

### ▪ Google Analytics 연결

[https://analytics.google.com/analytics/web/](https://analytics.google.com/analytics/web/)에서 접속하여 연결

```yml
# Analytics
analytics:
  provider: "google-gtag"
  # false (default), "google", "google-universal", "google-gtag", "custom"
  google:
    tracking_id: "your tracking id here" # 본인의 tracking id 입력
    anonymize_ip: # true, false (default)
```

### ▪ Goolge Search Console 연결

구글에 내 게시물이 보이게 하려면 search console과 연결이 필요
[https://search.google.com/search-console/about](https://search.google.com/search-console/about)에서 접속하여 도메인 등록

1. 도메인 등록 시 구글에서 제공하는 `google~~.html` 파일 루트 디렉토리에 업로드
2. `jekyll-sitemap` 플러그인 설치 (구글링 추천)

```bash
sudo gem install jekyll-sitemap
```

3. `_config.yml` 파일에 plugins에 jekyll-sitemap 없으면 추가

```yml
# Plugins (previously gems:)
plugins:
  - jekyll-sitemap
```

4. 루트 디렉토리에 `robots.txt` 생성

```txt
User-agent: *
Allow: /

Sitemap: https://github-account.github.io/sitemap.xml
```

### ▪ 네이버 검색 등록 (서치어드바이저)

[https://searchadvisor.naver.com/](https://searchadvisor.naver.com/)에 접속하여 사이트 등록  
루트 디렉토리에 `naver~~~~.html` 추가

- 참고할만한 블로그가 있어서 링크 걸어두겠습니다.
  [https://yenarue.github.io/tip/2020/04/30/Search-SEO/#%EB%84%A4%EC%9D%B4%EB%B2%84-naver](https://yenarue.github.io/tip/2020/04/30/Search-SEO/#%EB%84%A4%EC%9D%B4%EB%B2%84-naver)

### ▪ 폰트 변경

1. `assets/css/main.scss`에 import나 font-face 방식 중 선택하여 폰트 추가

```scss
@import url("https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");

@font-face {
  font-family: "RIDIBatang";
  font-weight: normal;
  src: url(/assets/css/fonts/RIDIBatang.otf);
}
```

2. `_sass/minimal-mistakes/_variables.scss`에서 폰트 설정

```scss
$serif: Georgia, Times, serif !default;
$sans-serif: -apple-system, BlinkMacSystemFont, "Apple SD Gothic Neo",
  "Montserrat", "Pretendard", "Merriweather", sans-serif !default;
$monospace: "Fira Mono", "Pretendard", Monaco, Consolas, "Lucida Console",
  monospace !default;
```

### ▪ About 페이지 작성

상단 네비게이션의 `About` 탭은 `_pages/about.md`로 연결. 해당 파일에 내용 작성

```txt
---
title: "Hi all! I'm OOOOOO👋🏻"
permalink: /about/
layout: single
comments: false
---




