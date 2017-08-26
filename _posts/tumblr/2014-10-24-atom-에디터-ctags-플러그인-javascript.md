---
layout: post
title: atom 에디터 ctags 플러그인 + javascript
date: '2014-10-24T15:39:00+09:00'
tags:
- ctags
- atom.io
- javascript
tumblr_url: http://think.golbin.net/post/100813499226/atom-에디터-ctags-플러그인-javascript
---
atom.io 의 디폴트 심볼뷰를 대체하는 atom-ctags 플러그인이 있었다. 아.. 이걸 여태 모르고 있었다니.. 털썩..OTL;;

https://github.com/yongkangchen/atom-ctags

이걸 사용하면 단축키를 사용해 함수 정의로 이동을 쉽게 할 수있는데, 자바스크립트의 경우 ctags 설정을 좀 해 줘야 멤버 함수 정의 같은 것도 찾아들어갈 수 있다. 아래는 내가 쓰는 ctags 인데, 맥 사용자의 경우 아래 내용을 ~/.ctags 안에 넣고 ctags 를 리빌드하면 이제부터는 멤버 함수도 쉽게 찾아다닐 수 있다.

--exclude=*.min.js
--exclude=.git
--exclude=node_modules
--exclude=vendors

--langdef=js
--langmap=js:.js
--regex-js=/[ \t.]([A-Z][A-Z0-9._$]+)[ \t]*=[ \t]*[0-9"''\[\{]/\1/n,constant/
--regex-js=/([A-Za-z0-9._$]+)[ \t]*=[ \t]*\{/\1/o,object/
--regex-js=/[''"]*([A-Za-z0-9_$]+)[''"]*[ \t]*:[ \t]*\{/\1/o,object/
--regex-js=/([A-Za-z0-9._$]+)\[["'']([A-Za-z0-9_$]+)["'']\][ \t]*=[ \t]*\{/\1\.\2/o,object/
--regex-js=/([A-Za-z0-9._$]+)\.prototype[ \t.=]/\1/c,class/
--regex-js=/([A-Za-z0-9._$]+)[ \t]*=[ \t]*\(function\(\)/\1/c,class/
--regex-js=/[''"]*([A-Za-z0-9_$]+)[''"]*:[ \t]*\(function\(\)/\1/c,class/
--regex-js=/var[ \t]*([A-Za-z$][A-Za-z0-9_$()]+)[ \t]*=[ \t]*function[ \t]*\(/\1/f,function/
--regex-js=/function[ \t]+([A-Za-z$][A-Za-z0-9_$]+)[ \t]*\(([^)])\)/\1/f,function/
--regex-js=/[''"]*([A-Za-z$][A-Za-z0-9_$]+)[''"]*:[ \t]*function[ \t]*\(/\1/m,method/
--regex-js=/([A-Za-z$][A-Za-z0-9_$]+)[ \t]*=[ \t]*function[ \t]*\(/\1/m,method/
--regex-js=/([A-Za-z0-9_$]+)\[["'']([A-Za-z0-9_$]+)["'']\][ \t]*=[ \t]*function[ \t]*\(/\2/m,method/
--regex-js=/([A-Za-z0-9._$]+)[ \t]*=[ \t]*\[/\1/a,array/
--regex-js=/[''"]*([A-Za-z$][A-Za-z0-9_$]+)[''"]*:[ \t]*\[/\1/a,array/
--regex-js=/([A-Za-z0-9._$]+)\[["'']([A-Za-z0-9_$]+)["'']\][ \t]*=[ \t]*\[/\1\.\2/a,array/


참고로 아래는 내가 쓰는 관련 단축키 추가 설정

''.editor'':
  ''ctrl-]'': ''atom-ctags:go-to-declaration''
  ''ctrl-['': ''atom-ctags:return-from-declaration''
  ''cmd-ctrl-n'': ''window:focus-next-pane''
  ''cmd-ctrl-k'': ''pane:split-right''
