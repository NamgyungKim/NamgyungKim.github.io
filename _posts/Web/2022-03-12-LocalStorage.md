---
title: "[Web API] 로컬스토리지에 데이터 저장, 삭제 하기"
sidebar_main: true
layout: single
categories: 
  - Web
tag: [Local Storage]
---


![이미지]({{ site.url }}{{ site.baseurl }}/assets/images/2022/03/12_1.png)  

<br />

## 로컬스토리지에 데이터 저장 및 제거

파일 하나에 로컬스토리지에 저장,삭제 하는 함수를 만들어서 export해서 사용하면 편하다.

<br />

![이미지]({{ site.url }}{{ site.baseurl }}/assets/images/2022/03/12.jpg)  

<br />

```js
// Local Storage에 저장


const setLocalData = (key, value) =>
  localStorage.setItem(key, JSON.stringify(value));

// Local Storage에서 Value 꺼내오기
const getLocalData = key => JSON.parse(localStorage.getItem(key));

// Local Storage 제거
const removeLocalData = key => JSON.parse(localStorage.removeItem(key));

// Local Storage 전체 항목 제거
localStorage.clear();

export { setLocalData, getLocalData, removeLocalData }
```

저장 시 속성을 수정하는 방식으로 하면 length,toString같은 내장 함수를 덮어씌울 수 있기 때문에
아래와 같은 setItem을 통해 추가하는 것을 권장한다.
```js
localStorage.key= 'value';
localStorage['key']='value';
localStorage.setItem('key', JSON.stringify('value')); // 👍권장
// localStorage에는 문자열만 저장 가능하므로JSON.stringify 해주는 것이 좋다.
```


<br /><br /><br /><br />

**< Refer to >**<br />

[velog:모듈 과 번들러 그리고 webpack](https://velog.io/@sunhwa508/%EB%AA%A8%EB%93%88-%EB%B2%88%EB%93%A4%EB%9F%AC-webpack)  
[의존성 관리](https://ui.toast.com/fe-guide/ko_DEPENDENCY-MANAGE)  
