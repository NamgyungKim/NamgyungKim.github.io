---
title: "[JS] 이벤트루프 와 태스크 큐(Callback Queue)"
sidebar_main: true
layout: single
categories: 
  - JavaScript  
tag: [js]
---

## JavaScript의 동작

JavaScript의 특징 중 하나는 <u>싱글 스레드</u>로 동작한다는 것이다.  
싱글 스레드 방식이라는 것은 한번에 하나의 태스크만 처리할 수 있음을 의미한다. 하지만 브라우저의 작동을 보면 많은 태스크가 한번에 작동하는 것 처럼 보인다. 예를 들면 HTML에서 애니메이션이 돌면서 동시에 HTTP요청을 하는등.. 어떻게 이런것이 가능할까?

> **태스크는** 프로그램 초기 시작, 이벤트 콜백 실행, 인터벌과 타임아웃 실행처럼 표준방식에 의해 예약된 아무 JavaScript코드이다. 태스크는 모두 태스크 큐에서 실행까지 대기한다.

<br />


## 이벤트루프 와 태스크 큐(Callback Queue)

아래 그림을 보면 기본적으로 JavaScript 앤진(크롬은 V8)에는 Heap과 Call Stack 이 두 영역으로 나뉜다.  
Heap은 메모리 공간이고, Call Stack에 실행컨텍스트가 쌓이고 위에서부터 순차적으로 실행된다.  
실행하다가 setTime out이나 setInterval, AJAX요청, Dom 등이 나타나면 WebAPIs에서 이것들을 처리한다.  
이렇게 비동기적으로 코드가 실행된다. 실행이 끝난 함수는 Callback Queue로 이동이된다.  
이렇게 쌓인 Callback Queue는 Call Stack이 비어 있으면 Event Loop가 Call Stack 으로 이동시키고 Call Stack으로 이동한 함수는 실행되게 된다.

![이미지]({{ site.url }}{{ site.baseurl }}/assets/images/2022/03/07.png)  
이미지 출처<https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf>

<br />


그렇다면 아래 코드를 실행시켰을 때 어떤 결과가 나올까?

```js
console.log('one');

setTimeout(function() {
  console.log('two');
}, 0);

console.log('three');
```

.  
.  
.  
**정답은**  
one  
three  
two  
이다. 

첫번째 ```console.log('one')``` 이 실행되고, 다음 setTimeout은 webAPIs가 처리하고 바로 Callback Queue에서 ```console.log('two')``` 가 대기상태로 있는다.  
이후 ```console.log('three')```가 실행되고 Call Stack이 비어지면 그제서야 Callback Queue에 있던 ```console.log('two')```를 이벤트루프가 Call Stack으로 옮기게 되고 마지막으로 ```console.log('two')```가 실행하게 된다.



<br /><br /><br /><br />

**< Refer to >**  
[Youtube/ZeroCho TV/노드교과서 개정판 2-2. 이벤트 루프 알아보기](https://www.youtube.com/watch?v=wRPcxR1M7Uc&list=PLcqDmjxt30RuRk0gcFwT_s7nexAYRF2_I&index=8)  
[JavaScript의 queueMicrotask()와 함께 마이크로태스크 사용하기](https://developer.mozilla.org/ko/docs/Web/API/HTML_DOM_API/Microtask_guide)  
[JavaScript | 자바스크립트 작동 원리(Event Loop와 Call Stack, Web API, Callback Queue)](https://velog.io/@xedni/JavaScript-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%9E%91%EB%8F%99-%EC%9B%90%EB%A6%ACEvent-Loop%EC%99%80-Call-Stack-Web-API-Callback-Queue)  
이웅모,『모던 자바스크립트 Deep Dive』, 위키북스, 2020