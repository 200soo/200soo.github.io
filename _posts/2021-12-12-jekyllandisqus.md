---
layout: post
title: jekyll 설치 및 disqus 적용 오류
subtitle: github blog making
categories: Jekyll
tags: [github, jekyll, disqus]
comments: True
---

### Jekyll 설치

먼저! 운영체제가 window라면? <br>
[Ruby+Devkit](https://rubyinstaller.org/downloads/)를 설치합니다.

이후 `gem install jekyll bundler` 명령어를 통해 Jekyll을 컴퓨터에 설치합니다. <br>
만일 Jekyll이 설치되었는지 확인하고자 한다면 `jekyll -v`로 확인할 수 있습니다.

github와 연결된 local repo에 본격적으로 jekyll 사이트를 생성합니다.
```
jekyll new . --force
```

주된 사이트 정보는 `_config.yml`에서 관리하므로 github에 관련된 사항들을 잊지 않고 입력해주어야 합니다. 특히 **disqus** 사용을 위해 `url:`을 입력해두어야 합니다.


### disqus 연동 오류

github 댓글 기능을 사용하기 위해서는 [disqus](https://disqus.com/)에 가입해야 합니다.

안내에 따라 jekyll 플랫폼 연동으로 들어가면 `_layouts/post`에 들어갈 코드를 제공하는 창이 뜨는데, disqus 연동에 지속적으로 오류가 나던 터라 연동에 관한 내용 대신 오류에서 문제가 되는 부분을 짚고 넘어가겠습니다.

1. 보안 문제
  - disqus는 허용된 도메인에서만 지원을 합니다. 만일 허용되지 않은 도메인에 연동을 하고자 한다면, 설정에서 정확한 블로그 이름을 적었더라도 댓글을 쓸 수 없는 상황이 벌어질 수 있습니다.
  - https://`shortname`.disqus.com/admin/settings/advanced/
  - 위 사이트에서 Trusted Domains에 도메인을 입력하면 사용이 가능해집니다.

2. url 오류
  - 만일 위의 보안 문제가 아니라면, `_config.yml`에 disqus의 shortname, comment 설정이 되지 않았거나 url을 입력하지 않은 경우이므로 해당 파일 열람이 필요합니다.