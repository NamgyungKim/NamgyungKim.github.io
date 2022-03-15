---
title: "[JS] 날짜 계산 방법 (방금전, 1시간전, 하루 전, 1년 전)"
sidebar_main: true
layout: single
categories: 
  - JavaScript  
tag: [js]
---

![이미지]({{ site.url }}{{ site.baseurl }}/assets/images/2022/03/15.jpg)

<br />

## js 시간 차이 계산

게시판에 보면 '방금전', 'x분 전' 이런 식으로 표기된다.  
몇분전에 표기되었는지를 파악하기 위해서는 지금 현재시간과 작성시간을 비교해야한다.  
현재시간과 이전시간 비교를 위해서 현재시간과 작성시간을 getTime()으로 날짜를 초단위로 변경 후 이 둘을 빼주는 형식으로 구혔했다. 

<br />

```js
const elapsedTime = date => {
  const nowDate = new Date().getTime(); //지금시간
  const elapsedMSec = Math.floor((nowDate - date) / 1000);
  const elapsedMin = Math.floor(elapsedMSec / 60);
  const elapsedHour = Math.floor(elapsedMin / 60);
  const elapsedDay = Math.floor(elapsedHour / 24);

  if (elapsedMSec < 60) {
    return '방금 작성';
  } else if (elapsedMin < 60) {
    return `${elapsedMin} 분 전`;
  } else if (elapsedHour < 24) {
    return `${elapsedHour}시간 전`;
  } else if (elapsedDay < 30>){
    return `${elapsedDay}일 전`;
  } else {
    return `1달 이전`
  }
};
```


<br /><br /><br /><br />
