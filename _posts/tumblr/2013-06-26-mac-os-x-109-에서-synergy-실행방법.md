---
layout: post
title: Mac OS X 10.9 에서 Synergy 실행방법
date: '2013-06-26T13:12:07+09:00'
tags:
- mac os x
- mavericks
- synergy
tumblr_url: http://think.golbin.net/post/53901051302/mac-os-x-109-에서-synergy-실행방법
---
Mac OS X 10.9 에서 Assistive Control 기능이 변경됨에 따라, Synergy(서버)가 제대로 작동하지 않고 있습니다. 업데이트로 해결되겠지만, 일당 당장 사용하는 방법은 터미널을 사용하시면 되는데요.

응용프로그램->유틸리티->터미널을 여시고, 다음의 명령어를 넣으시면 됩니다.

/Applications/Synergy.app/Contents/MacOS/synergys -f -c /Users/golbin/synergy.conf

synergy.conf 는 Synergy 를 여시고 맞는 설정을 하신 뒤에, File->Save confi… 를 이용해서 저장하시면 됩니다.
