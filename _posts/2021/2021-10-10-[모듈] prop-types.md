---
title: "[모듈] porp-types"
layout: single
categories: React
tag: [모듈, React, prop-types]
---

<br />

## prop-types
prop-types는 전달받은 데이터의 type이 의도된 바와 일치하는지를 검사해주는 모듈이다.

## type 검사를 왜 할까?
: 작업하는 프로젝트의 규모가 커질수록 예상치 못한 곳에서 에러가 발생하는 일이 많아진다.
이때, 수많은 데이터를 전달하고 받다 보면 전달받지 말아야 할 타입을 받는 등의 에러가 발생하기도 한다.<br />
이를 방지하고자 받는 데이터의 타입을 지정해 주면 받지 말아야 할 타입을 받았을 경우 에러 메시지창을 띄운다.
개발자들은 이 경고 메시지를 보고 좀 더 수월하게 문제 원인을 찾고 에러를 고칠 수 있게 된다.<br />
만일 이런 타입 검사를 하지 않았을 경우, 많은 시간을 에러를 찾기 위해 쏟아부어야 할지도 모른다.

<br />

## 사용법

```powershell
$ npm i prop-types
```

```javascript
import PropTypes from 'prop-types';

Component_name.propTypes = {
    name: PropTypes.string.isRequired 
    // isRequired를 붙이면 값을 받아오지 않을 경우에 에러창을 띄움.
    array: PropTypes.arrayOf(PropTypes,number) // 배열의 경우
    object: PropTypes.shape({
      name: PropTypes.string.isRequired,
      age: PropTypes.number.isRequired
    }) // 객체의 경우
    num: PropTypes.string.isRequired // Warning!!
}
```

Warning!!
![error]({{ site.url }}{{ site.baseurl }}/assets/images/2021-10/error.png)

<br />
<br />
<br />
<br />


**< Refer to >**<br />
[npm: prop-types](https://www.npmjs.com/package/prop-types)

