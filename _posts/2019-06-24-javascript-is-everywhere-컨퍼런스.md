---
bg: 'any_story2.jpg'
layout: post
title: "Javascript is Everywhere 컨퍼런스"
crawlertitle: "Javascript is Everywhere"
summary: "Javascript is Everywhere"
date: 2019-06-24
categories: posts
tags : ['Storys']
author: "Young"
---

 2019 JavaScript is Everywhere 컨퍼런스에 가서 흥미롭게 들었던 주제들을 끄적여본 글입니다.

 우연히 페이스북에서 Js 커뮤니티에 개최하는 컨퍼런스를 보게 되었는데, 꽤나 유명한 분들이 많이 오고 js 개발에 대해 유익한 정보를 많이 얻을 수 있을 것 같아서 6월 22일 광화문에서 열리는 Javascript is Everywhere 컨퍼런스에 참여하게 되었다.

 여러가지 세션에서 강의를 들었지만 그 중에서도 가장 인상 깊게 본 것들을 써보자고 한다.

<br/>

#### Electron 시작부터 배포까지 / 김동우

 먼저 세션 #1 때 봤던 김동우 개발자님이 발표해주신 Electron이다. 사실 Electron을 아직 관심있게 본적이 없고 당연하지만 해본 적이 없었다. 그치만 예전부터 가끔 주변에서 이야기하는 것을 들었고 웹을 응용소프트웨어 처럼 사용할 수 있다는 것을 듣고 이번 기회에 들어보자 하는 마음으로 발표장에 들어갔다. 

 발표에 내용은 Electron을 빠르게 시작하는 방법과 Electron의 구조, 작동 방식과 프로덕션 환경에서는 어떤 방식을 이용해야 보안에 취약점을 줄일 수 있는 지에 대한 방법에 대해 발표 하셨다. 

![KakaoTalk_20190623_194734530](https://user-images.githubusercontent.com/38432821/60003226-384f4480-96a5-11e9-84c7-f267f117369e.jpg)

사실 위에서 말했던 것 처럼 한번도 해본적이 없었기 때문에 김동우 개발자님이 말해주신 팁이나 취약점 보안에 대해 정확히 알아 듣지는 못했지만 Electron이 작동하는 방식이나 어떤 경우에 개발하여 사용하였을 때, 사용자들이 편리하게 사용할 수 있는 지에 대해 알게되는 계기였다.

<br/>

#### 나의 JavaScript 사용기 / 최종욱

 이 발표에서는 개발에 대한 이야기 보다는 "우리가 왜 Javascript를 하게 되었는가?" 와 "좋은(Great) 개발자란 무엇인가" 에 대한 이야기식의 발표가 진행 되었다. 개인적으로 필자는 JS 개발을 쉽고 간단해서~~(겉만 그런거였어)~~ 시작하게 되었는 데, 사용하다 보니 JS를 사용할 수 있는 분야(인공지능, 블록체인 등)가 많았고 사실 다른 언어보다 배우는 것이 즐거웠던 것 같다. 그리고 발표를 하면서 중간에 "개발을 잘하는, 좋은 개발자란 무엇인가"에 대해 이야기 하였는데, 한가지 질문을 하셨다.

> 우리가 사용하는 기술을 이용하여 무언가를 만드는 개발자가 개발을 잘하는 개발자인가,
> 
> 아님 우리가 사용하는 기술을 만들어 내고 혁신해내는 개발자가 개발을 잘하는 개발자인가

 이 질문을 듣고 잠깐 갸우뚱하긴 하였지만 두 개발자 모두 좋은 개발자라고 생각한다. 기술을 만들어도 그 것을 이용해 이로운 서비스를 만드는 개발자가 없다면 결국 그 기술은 도태되기 마련이기 때문이다. 하지만 모든 개발자가 현재 기술에 적응하는 개발자가 아닌 기술을 만들어 내기도 하고 응용도 할 줄 아는 사람이 되어야 한다고 생각한다. 비록 특정 언어, 기술에 대한 팁을 얻을 수는 없었지만 이 발표를 들으면서 1년동안 개발을 왜 하고 어떻게 하게 됬는 지에 대해 또한 좋은 개발자에 대해 생각 하는 좋은 계기가 되었다.

<br/>

#### React Hooks + TS + functional = 아름다움 / 유윤재

 마지막으로 들었던 강의로 유윤재 개발자님이 React Hooks + Ts + functional 이라는 주제로 강의를 해주셨다. 이번에는 React 코드와 많이 밀접해 있는 강의였고 가장 기대되었던 강의 중 하나 였다. 예전에는 class component를 주로 사용하여서 React를 개발하였다면. 최근 16.8 업데이트에서 Hooks 라는 기술이 나오면서 React의 새로운 패러다임이 불기 시작했다. Hooks를 사용하면 functional component 에서도 state를 관리할 수 있었고 이전에 함수형에서 사용하지 못했던 라이프 사이클(Lifecycle)를 **useEffect**를 이용하여 사용할 수 있게 되었다. 그 밖에도 Typescript를 이용하면 이전에 propTypes로 타입을 작성했던 것 보다 편리하게 props에서 받는 타입을 정의할 수 있게 된다. 또한 Typescript는 이번에 나온 Hooks에도 적용하여 사용할 수 있기 때문에 Front 개발에 Typescript는 필수라고 생각이 든다.

![image](https://user-images.githubusercontent.com/38432821/60058788-ba328280-9724-11e9-8542-bf720b69ae44.png)

※ 가서 들었던 코드와 관련된 것들은 나중에 블로그에 다시 정리할 계획이다.

<br/>

##### 마치며 ...

 컨퍼런스르 모두 마치고 든 생각이지만 단순히 js의 특정 분야, 특정 부분에 너무 강의가 치우쳐져 있다는 생각이 들었고 조금은 듣는 개발자 분들의 수준을 고려하여 기본적인 것들은 빼는 것이 좋다는 생각을 했다.(당연한 것들을 설명하느라 시간을 잡아먹은 강의가 몇개 있었다.) 전체적으로 조금 아쉬웠던 부분이 있지만 여러가지 개발, 테스팅 할 때, 쓰면 좋은 팁들을 알 수 있는 좋은 시간이였던 것 같다.
