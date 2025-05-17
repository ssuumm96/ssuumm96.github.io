---
title:  "[Jekyll] Github 블로그 만들기.."
excerpt: "md 파일에 마크다운 문법으로 작성하여 Github 원격 저장소에 업로드"

categories:
  - Blog
tags:
  - [Blog, jekyll, Github, Git]

toc: true
toc_sticky: true

date: 2020-05-25
last_modified_at: 2020-05-25
---

Minimal Mistakes 테마 사용
https://velog.io/@eona1301/Github-Blog-Jekyll-minimal-mistakes-%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0
참고

1.
https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/
Minimal Mistakes remote theme starter 링크 찾아서 클릭
"username".github.io

2.
블로그에 카테고리와 테그, 연도 아카이브로 분류하는 설정
github.io Repository 에 _pages 디렉토리를 생성하고, category-archive.md, year-archive.md, tag-archive.md 파일을 생성
나는 tag는 안 만들음

3.
_data 디렉토리의 navigation.yml 수정


###검색기능 추가
1. layout Seach 기능 사용 (현재 사용중인 방법)

* _data/navigation.yml 수정
	main:
  - title: "Search"
 url: "/search/"

* _pages/search.md 파일 생성
---
title: Search
layout: search
permalink: /search/
author_profile: true
sidebar:
 nav: "sidebar-category"
---

2. lunr 사용

* _config.yml 수정
search                   : true # true, false (default)
search_full_content      : true # true, false (default)
search_provider          : "lunr" # lunr (default), algolia, google
lunr:
  search_within_pages    : # true, false (default)