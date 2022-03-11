---
title: "[Web API]로컬스토리지에 저장, 삭제"
sidebar_main: true
layout: single
categories: 
  - Web API 
tag: [번들링, webpack]
---

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




<br /><br /><br /><br />

**< Refer to >**<br />

[velog:모듈 과 번들러 그리고 webpack](https://velog.io/@sunhwa508/%EB%AA%A8%EB%93%88-%EB%B2%88%EB%93%A4%EB%9F%AC-webpack)  
[의존성 관리](https://ui.toast.com/fe-guide/ko_DEPENDENCY-MANAGE)  
