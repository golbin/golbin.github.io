---
layout: post
title: pushd/popd
date: '2015-02-09T03:56:00+09:00'
tags:
- linux
- pushd
- popd
tumblr_url: http://think.golbin.net/post/110460141766/pushdpopd
---
리눅스/유닉스(물론 맥도)의 명령어 중에 은근히 유용하지만 의외로 많이 모르는 명령어들이 좀 있다. 그 중 최근에 팀원에게 가르쳐 준 명령어가 있는데 바로 pushd/popd라는 명령어다.

아주 간단한 명령어로, pushd로 다른 디렉토리로 이동했다가 popd로 다시 현재 디렉토리로 돌아오는 콤비 명령어다.

예를들어, 내가 현재 작업하고 있는 디렉토리가 /usr/local/lib/node_modules/lodash 인데, nginx 설정을 좀 바꾸러 /etc/ngnix/conf.d 로 갔다가 오려면, 일반적으로는 다음 조합의 명령어를 써야할 것이다.

pwd (경로 확인 및 복사)
cd /etc/ngnix/conf
cd conf.d
cd …
cd /usr/local/lib/node_modules/lodash
하지만 pushd/popd 를 이용하면

cd /etc/ngnix/conf
cd conf.d
cd …
popd
끝! 엄청 편하지 않은가? ㅎㅎ 참고로 pushd를 연속으로 사용하고 popd로 순서대로 돌아올 수도 있다.

물론 로컬 컴퓨터에서 작업한다면 터미널을 새로 띄워서 작업하거나, screen 등으로 작업하는 방법도 있지만, 그래도 기억해두면 서버작업을 하거나 할 때 꽤 유용하게 쓰일 일이 많은 명령어이니 기억해두면 좋을 것이다.

추가. 바로 전 디렉토리로만 돌아가는 것은 cd -라고만 하면 된다.
