---
layout: post
title:  "Jekyll(자킬) 로 github.io 발행하기 #1"
date:   2018-11-25 17:30:00 +0900
categories: [jekyll]
---
# Jekyll(자킬) 로 github.io 발행하기 #1

## 목표 정하기
- Jekyll 이 어떻게 동작하는지 파악해보기
- Azure 에 Jekyll 이 동작하는 머신 만들기
- [Tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/) 을 따라하면서 가장 심플한 동작 파악하기
- 테마를 정하고 github.io 에 연결하기
- 실제 발행하기

# Work Log

## Azure 에 Jekyll 동작 환경 만들기
- Azure ubuntu 가상머신 만들기 참조
- [Jekyll on Ubuntu](https://jekyllrb.com/docs/installation/ubuntu/) 를 따라하니 별 어려움 없이 잘 설치 됨

## Tutorial 따라하기
- 큰 어려움 없이 파일 변경이 실시간으로 적용되어서 매우 편했음
- Azure 에 TCP 4000 Port 가 모든 IP 에서 접속할 수 있도록 환경 수정
- 외부에서 접속 할 수 있게 하기 위해서 Host 옵션만 추가하여 실행함

```bash
$ jekyll serve -H 0.0.0.0
```

## 테마를 정하기
- 다음 2개의 사이트에서 여러 테마를 찾아 보았음
  - https://jekyllthemes.io/free
  - http://jekyllthemes.org/
- 마음에 드는 몇가지 테마들
  - https://volny.github.io/creative-theme-jekyll/
  - https://phlow.github.io/feeling-responsive/
  - http://wiredcraft.github.io/carte/
  - http://jekyller.github.io/jasper/
  - https://agusmakmun.github.io/
  - http://vfalanis.github.io/taken/

## GITHUB.IO 에 배포할 준비하기
### 기술적인 고민에 참고했던 몇몇 국내 블로그
- https://www.theteams.kr/teams/2440/post/67297
- http://jihyeleee.com/blog/third-designer-can-make-jekyll-blog/
- https://github.com/ridicorp/ridicorp.github.io

### markdown 에디터 찾아보기
- [macdown](https://macdown.uranusjr.com/)
  - 다 좋은데 이미지의 연결이 jekyll 와 적절하게 연동이 되지 않는다.

### github 에 repository 만들어서 적용해보기
- 가급적 문제되는 충돌을 피하기 위해서 별다른 파일을 만들지 말자
- .gitignore 에 jekyll 테마가 있다.
- repository 를 만들고 보니 가급적(?) 만들어진 테마를 fork 하는 것이 좋을 수도 있겠는데, 일단 만들어보고 고민하기로 ...
- 그래서 zip 파일을 받아서 일일히 파일을 맞춰주기로 함

### 실제 배포해보기
- 만들어둔 Azure 머신에 repository 갱신
```bash
$ git clone https://github.com/iz4blue/iz4blue.github.io
$ cd iz4blue.github.io
```
- 설치되어 있지 않는 jekyll plugin 설치 되도록 bundle install 을 수행함
```bash
$ bundle install
```
- 예전부터 참 골치 아프게 했던 [nokogiri](https://www.nokogiri.org/) 이번에도 문제가 되는 상황
- 찾아보니 라이브러리가 없어서 생기는 문제군요.
  - https://www.hahwul.com/2018/03/ruby-nokogiri-installupdate-error.html
```bash
$ sudo apt-get install zlib1g-dev
```

### 이제 작성하던 내용을 확인해보자
- 일단 잘 동작하는지 확인
```bash
$ jekyll serve -H 0.0.0.0
```
- 브라우져로 접속해서 페이지가 원하는데로 뜨는지 확인

### 이제 static page 들을 만들어서 발행하자
- 공식 페이지에서 이야기 하는 것 처럼 일단 build 해보자
```bash
$ JEKYLL_ENV=production bundle exec jekyll build
```
- 