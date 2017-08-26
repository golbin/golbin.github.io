---
layout: post
title: Mac OS X 에서 gnu split 를 사용하는 방법
date: '2013-08-07T21:33:15+09:00'
tags: []
tumblr_url: http://think.golbin.net/post/57607557067/mac-os-x-에서-gnu-split-를-사용하는-방법
---
Mac OS X 에 기본으로 포함되어 있는 split 유틸리티에는 나누어서 저장할 파일 이름의 접미사를 숫자형으로 쓸 수 있는 옵션이 없습니다.

이 옵션을 사용하기 위해서는 gnu split 를 깔아서 사용해야 하는데요.

brew 를 사용하면 간단하게 사용하실 수 있습니다.

brew 를 설치한 상태에서 다음과 같은 명령어로 coreutils 를 설치하시면,

brew install coreutils


이후 gsplit 명령어로 더 다양한 옵션의 split 유틸리티를 사용하실 수 있습니다.
