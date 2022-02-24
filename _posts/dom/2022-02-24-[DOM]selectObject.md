---
title: "[DOM] Dom요소 선택하기"
sidebar_main: true
layout: single
categories: 
  - DOM  
tag: [dom,모던자바스크립트]
---

HTML의 구조나 내용 또는 스타일 등을 동적으로 조작하려면 먼저 요소 노드를 취득해야 한다.  
이때 선택자 API는 DOM에서 Element 노드를 선택자를 통해 빠르고 쉽게 가져올 수 있는 메서드를 제공한다.    

# id를 이용한 요소 노트 취득

- 만약 id가 여러개 존재할 경우 가장 첫번째 요소 하나만 반환한다.  
- 만약 해당 id가 없다면 null을 반환한다.  
- querySelector가 getElementById보다 조금 느리다고 한다.

```js
const elem = document.getElementById('elem')
const elem2 = document.querySelector('#elem2')
```
- HTML 요소에 id 어트리뷰트를 부여하면 id 값과 동일한 이름의 전역 변수가 암묵적으로 선언되고 해당 노드 객체가 할당되는 부수 효과가 있다.

```html
<body>
  <div id="foo"></div>
  <script>
    //아이디와 동일한 이름의 전역변수가 암묵적으로 선언되고 해당 노드 객체가 할당된다.
    console.log(foo) // <div id="foo"></div>

    // 암묵적 전역으로 생성된 전역 프로퍼티는 삭제되지만 전역 변수는 삭제되지 않는다.
    delete foo
    console.log(foo) // <div id="foo"></div>

    // id 값과 동일한 이름의 전역변수가 이미 선언되어 있으면 노트 객체가 재할당되지 않는다.
    let foo = 1
    console.log(foo) // 1
  </script>
</body>
```



<br /><br /><br /><br />

**< Refer to >**<br />

이웅모,『모던자바스크립트Deep Dive』, 위키북스, 2020.9, 39장 DOM 685p~709p  
[MDN Web Docs: 선택자로 Dom 요소 선택하기](https://developer.mozilla.org/ko/docs/Web/API/Document_Object_Model/Locating_DOM_elements_using_selectors)