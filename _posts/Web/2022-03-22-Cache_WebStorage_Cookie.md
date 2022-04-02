---
title: "[Web] 웹 저장소들의 특징(Web Storage, Cookie, Cache)"
sidebar_main: true
layout: single
categories: 
  - Web
tag: [Local Storage]
---

![이미지]({{ site.url }}{{ site.baseurl }}/assets/images/2022/03/22_2.png)

<br />

# 📖 [Web] 웹 저장소들의 특징(Web Storage, Cookie, Cache)

개발자 모드를 보면 Application탭에 Storage를 볼 수 있다.  
Local Storage, Session Storage, Cookies 등 이 브라우저 저장소는 앱또는 웹에 방문한 유저들에 대한 정보를 저장해준다.
**글을 임시로 저장**하거나, 그외 **서버에 저장할 필요가 없는데이터를 저장**한다.

![이미지]({{ site.url }}{{ site.baseurl }}/assets/images/2022/03/22.jpg)

<br />

## 💡 Cookie 
- 만료기간(지정가능) 동안 **일시적**으로 데이터를 저장할 수 있다.   
- http 요청 시 헤더에 쿠키가 같이 나가기 때문에 쿠키의 사이즈가 커지면 요청할 때 나가는 헤더도 커지게 된다.  
- 브라우저를 닫아도 데이터가 유지된다.   
- 클라이언트에서 자체적으로 조작할 수 있으며, 보안이 낮다.  
- 각 데이터별로 다음과 같은 옵션을 설정할 수 있다. 

![이미지]({{ site.url }}{{ site.baseurl }}/assets/images/2022/03/22_1.jpg)

<br />

|옵션|설명|
|:---:|---|
|Domain|도메인이 일치하는 요청만 쿠키 전송|
|Path|path와 일치하는 요청만 쿠키가 전송된다.|
|Expires|쿠키의 만료날짜|
|Max-Age|쿠키의 수명, 이때 Expires는 무시된다.|
|HttpOnly|JS에서 쿠키에 접근하지 못하도록 막는다.|
|Secure|HTTPS에서만 쿠키를 전송한다.|

<br />

## 💡 Web Storage
- 웹스토리지는 하기 힘든 것들을 지원하며 HTML5 부터 등장했다.  
- 로컬 스토리이와 세션 스토리지가 있다. 

### Sesstion Storage   
- key,Value타입의 저장소
- http프로토콜을 사용하는 사용자가 어떤 웹사이트를 방문할 경우, 사용자와 서버 사이의 연결을 확인 하기위한 정보 이다.  
- 서버에 직접저장되며 **브라우저가 종료되면 지워진다.**   
- 대신 보안성이 좋다.   

### Localstorage  
- key,Value타입의 저장소, 기능지원이 얼마 없다.  
- localStorage에는 string만 넣을 수 있다. 
- 도메인이 같다면 다른 탭안에서 같은 storage를 공유한다. 
- 데이터의 만료기간이 없으며 사용자가 지우지 않는 한 **영구적으로 보존**된다.  
- 설정을 저장하거나, 브라우저를 닫고 열었을때도 보관되어야하는 데이터를 저장할 때 사용된다.  

  [🔗 Localstorage 저장,삭제](https://namgyungkim.github.io/web/LocalStorage/)

<br />

## 💡 Cache
- 리소스파일들의 임시 저장소, 웹페이지를 접속할 때 **로드속도를 개선** 해준다. 
(css,js, 이미지, 비디오등 같은)

<br />

## 💡 IndexedDB
- key,Value타입으로 저장이된다.  
- 많은 양의 데이터를 저장하기에 적합하며 영구저장이 가능하다.  
- indexedDB에서의 데이터를 넣고 조회하는 과정이 비동기 이다.  


<br /><br /><br /><br />

**< Refer to >**  
<https://velog.io/@dorazi/쿠키-웹-스토리지-로컬-스토리지-세션-스토리지>  
 