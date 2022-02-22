---
title: "[DOM] Dom이란?"
sidebar_main: true
layout: single
categories: 
  - DOM  
tag: [dom,모던자바스크립트]
---



# DOM ( Document Object Model )

우리가 작성한 HTML 문서는 브라우저의 렌더링 엔진을 통해 HTML문서를 파싱(해석)하게된다.  
그렇게 파싱이 끝나면 브라우저가 이해할 수 있는 자료구조인 DOM을 생성하게된다.  
(이때 브라우저마다 다른 랜더링엔진을 사용하며 성능이나 세세한 부분이 조금씩 다를 수 있다.)  
DOM은 우리가 작성한HTML 문서의 구조와 정보를 객체형식으로 표현되어있으며, 이를 제어할 수 있는 API 즉, 프로퍼티와 메서드를 제공한다. 

![dom tree]({{ site.url }}{{ site.baseurl }}/assets/images/2022/02/22_1.png)

위 DOM트리 구조를 보면 모든 node는 EventTarget를 상속 받는다.    
그렇기 때문에 모든 요소에서 이벤트를 발생시킬 수 있게된다.  
<br />

## DOM요소 조작

DOM에는 많은 속성과 메소드가 존재한다. 이를 우리는 JS를 통해서 조작이 가능하다.  
DOM요소를 조작하기 위해서는 먼저 DOM에 접근해야한다.  

CSS에서는 class,id,태그 등의 선택자를 이용해서 스타일을 준다.  
js에서 DOM을 조작할때도 class,id,태그를 이용하여 접근하게된다.  

접근방식으로는 아래와 같은 방법들이 있다.  
```js
const p = document.getElementsByTagName('p')
const user = document.getElementById('user')
const student = document.getElementByClassName('student')
const selectId = document.querySelector('#select')
const selectClass = document.querySelector('.select')
```

접근 후에는 다양한 여러 메소드들로 dom을 조작할 수 있게 된다.
```js
//ex
//이벤트 추가
const selectId = document.querySelector('#select')
selectID.addEventListener('mouseover', mouseoverEvent )
const mouseoverEvent = () => console.log('mouseover')

//요소 생성
const create = document.createElement('div')
document.body.append(create)
```



<br /><br /><br /><br />

**< Refer to >**<br />

이웅모,『모던자바스크립트Deep Dive』, 위키북스, 2020.9, 39장 DOM 677p~700p
[dom tree 이미지|주요노트 프로퍼티](https://ko.javascript.info/basic-dom-node-properties)
