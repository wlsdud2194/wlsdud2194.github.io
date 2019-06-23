---
bg: "jekyll_img.png"
layout: post
title:  "Hello Jekyll !"
crawlertitle: "Hello Jekyll !"
summary: "첫 포스트"
date: 2019-02-11 
categories: posts
tags: 'Tips'
author: Young
---
2일 동안 고된 구글링과 영어문서를 읽어가면서 드디어 jekyll 테마를 적용하여 나만에 블로그에 포스트를 작성할 수 있게 되었다. 사실 이전에도 도전해보았지만 이해안되는 영어문서와 온갖 에러에 ~~빠른 손절을~~ 포기를 했었지만 방학이 되면서 다시 해보기로 하여 끝내 블로그를 완성했다.



**Jekyll**를 이용하여 블로그를 만들면서 가장 어려웠던 것은 테마 적용이였다. 맘에 드는 테마가 있어도 막상 다운로드하여 서버를 켜보면

```
Traceback (most recent call last):
        15: from C:/Ruby25-x64/bin/jekyll:23:in `<main>'
        14: from C:/Ruby25-x64/bin/jekyll:23:in `load'
        13: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/jekyll-3.8.5/exe/jekyll:11:in `<top (required)>'
        12: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/jekyll-3.8.5/lib/jekyll/plugin_manager.rb:50:in `require_from_bundler'
        11: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-2.0.1/lib/bundler.rb:107:in `setup'
        10: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-2.0.1/lib/bundler/runtime.rb:20:in `setup'
         9: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-2.0.1/lib/bundler/runtime.rb:108:in `block in definition_method'
         
 ...
```

????????

알 수 없는 에러가 발생 했습니다...



루비를 한번도 한적이 없었기 때문에 구글링에 의존해 검색을 해본 결과 생성한 프로잭트에서 요구하는 jekyll 버전과 현재 설치된 버전이 달라서 발생한 에러 였다. (구글 曰)

bundler를 설치하여 해결할 수 있지만 이것 저것 설치하는 것은 맘에 들지 않았기 때문에 버전에 맞는 다른 테마를 이용하여 블로그를 완성하였다.
<br/>
<br/>
#### 마치며

앞으로 공부하면서 알게된 것과 프로젝트 하면서 알게된 것들을 주로 포스팅할 예정이다.
