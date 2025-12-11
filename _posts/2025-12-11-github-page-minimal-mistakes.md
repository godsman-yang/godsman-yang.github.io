---
layout: post
title: 'GitHub Page 테마 변경 - Minimal Mistakes'
date: 2025-12-11 12:00
categories: github
---

기존 Jasper2 테마에서 Minimal Mistakes 테마로 변경했습니다.
AI 에이전트(Claude Code)를 활용해서 테마 마이그레이션 작업을 진행했습니다.

# GitHub Pages 프레임워크 선택

## 프레임워크 비교
GitHub Pages용 기술 블로그/문서 사이트 구축을 위한 프레임워크를 비교했습니다.

| 프레임워크 | 언어 | 특징 |
|-----------|------|------|
| Jekyll | Ruby | 테마 최다, GitHub Pages 기본 지원 |
| Hugo | Go | 테마 품질 최고 (PaperMod, Docsy) |
| Docusaurus | React/JS | 문서용 고품질 테마, AI Agent 연동 유리 |
| VitePress | Vue/JS | SPA 기반, UI 확장성 |

## 선택 기준
* 모든 후보(Jekyll, Hugo, Docusaurus, VitePress)는 정적 사이트 생성기
* Jekyll/Hugo: 정적 HTML 중심 → JS 위젯 추가는 가능하지만 확장성 제한
* Docusaurus/VitePress: React/Vue 기반 SPA → AI Agent 연동 및 UI 확장에 유리

## 언어 요구 수준
* Ruby/Go는 몰라도 가능
* JS를 알면 Docusaurus/VitePress 확장성이 매우 높아짐
* 마크다운 파일 작성해서 올리는 구조는 동일

## 최종 선택: Jekyll
* 기술 블로그 중심이라 Jekyll 유지
* GitHub Pages 기본 지원으로 별도 빌드 설정 불필요
* 테마 다양성 최고

# 테마 선택: Minimal Mistakes

## Jekyll 테마 비교
* **Minimal Mistakes** - 가장 인기 있는 Jekyll 테마, 문서화 우수
* **Chirpy** - 깔끔한 디자인, 사이드바 지원
* **Jasper2** - Ghost 테마 포트, 이전에 사용했던 테마

## Minimal Mistakes 선택 이유
* GitHub Pages remote_theme 지원 (로컬 빌드 불필요)
* 9가지 스킨 제공 (default, air, dark 등)
* 검색, TOC, 카테고리/태그 아카이브 등 기능 풍부
* 활발한 유지보수 (v4.27.3, 2025년 기준)

# 작업 과정

## 1. 백업
기존 폴더를 백업합니다.
```bash
cp -r godsman-yang.github.io godsman-yang.github.io.backup
```

## 2. _config.yml 변경
Minimal Mistakes 설정으로 변경합니다.
```yaml
# Theme
remote_theme: "mmistakes/minimal-mistakes@4.27.3"
minimal_mistakes_skin: "default"

# Site Settings
locale: "ko-KR"
title: "godsman-yang"
url: "https://godsman-yang.github.io"

# Permalink (기존 URL 유지)
permalink: /:title/

# 플러그인
plugins:
  - jekyll-paginate
  - jekyll-sitemap
  - jekyll-feed
  - jekyll-include-cache
```

## 3. Gemfile 변경
GitHub Pages 호환 설정으로 변경합니다.
```ruby
source "https://rubygems.org"

gem "github-pages", group: :jekyll_plugins
gem "jekyll-include-cache", group: :jekyll_plugins
```

## 4. 필수 파일 생성

**index.html**
```yaml
---
layout: home
author_profile: true
---
```

**_data/navigation.yml**
```yaml
main:
  - title: "About"
    url: /about/
```

**_pages/about.md**
```yaml
---
title: "About"
permalink: /about/
layout: single
author_profile: true
---
```

## 5. 불필요한 파일 삭제
Jasper2 테마 관련 파일들을 삭제합니다.
* _includes/
* _layouts/
* _plugins/
* .travis.yml
* gulpfile.js
* package.json

# 적용

## GitHub에 배포
```bash
git add .
git commit -m "Migrate to Minimal Mistakes theme"
git push
```

GitHub Actions가 자동으로 빌드합니다. 1~2분 후 사이트 확인 가능합니다.

## 결과
* 기존 21개 포스트 URL 유지 (permalink: /:title/)
* 기존 이미지 경로 유지 (assets/images/)
* 반응형 디자인 적용
* 저자 프로필 사이드바 추가

# 추가 기능 설정 방법

## 스킨 변경
_config.yml에서 한 줄 수정:
```yaml
minimal_mistakes_skin: "dark"  # default, air, aqua, contrast, dark, dirt, neon, mint, plum, sunrise
```

## 검색 기능
```yaml
search: true
search_full_content: true
```

## 목차(TOC) 자동 생성
```yaml
defaults:
  - scope:
      path: ""
      type: posts
    values:
      toc: true
      toc_label: "목차"
      toc_sticky: true
```

## 카테고리/태그 아카이브
_pages/category-archive.md 생성:
```yaml
---
title: "카테고리"
layout: categories
permalink: /categories/
---
```

# 참고 자료
* [Minimal Mistakes Quick-Start Guide](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)
* [Minimal Mistakes GitHub](https://github.com/mmistakes/minimal-mistakes)
* [GitHub Pages 문서](https://docs.github.com/en/pages)

# AI 에이전트 활용
이번 마이그레이션은 Claude Code를 사용해서 진행했습니다.
* 프레임워크/테마 선택 조사
* 마이그레이션 계획 수립
* 파일 생성 및 수정
* 문서 작성

AI 에이전트를 활용하면 반복적인 작업을 빠르게 처리할 수 있습니다.
