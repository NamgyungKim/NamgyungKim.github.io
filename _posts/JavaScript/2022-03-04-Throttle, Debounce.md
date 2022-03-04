---
title: "[JS] 디바운스(Debounce)와 스로틀(Throttle)"
sidebar_main: true
layout: single
categories: 
  - JavaScript  
tag: [js, Debounce, Throttle, 무한스크롤]
---



# 디바운스(Debounce)와 스로틀(Throttle)이란  

둘 다 Dom이벤트의 실행을 제어하는 방법이다.  
예를 들어 resize, scroll 를 했을때 어떤 이벤트가 실행한다고 했을 이벤트 수행에 제약을 걸어 보다 적은 이벤트가 실행되도록 한다.  

### 사용되는예
- 검색어 작성하는 중간중간 서버에 데이터를 요청할때  
  (검색기능 이용 시 작성하는 검색어에 따라 추천 검색어를 띄워줄 때 타자치는 모든 순간에 요청을 보내는건 비효율적이다.)
- 무한스크롤 (스크롤 위치를 측정 후 api 호출)
- 앱에서 요소를 드래그 할때 성능을 높이기 위해서


<br />

## 디바운스(Debounce)

디바운스는 이벤트를 방생 시키는 동안에는 
발생하는 이벤트를 무시하다가 정해둔 일정시간이 지나면 마지막에 발생한 이벤트 하나만 발생시키도록하는 기술이다.
- 예) 사용자가 텍스트를 입력 하다가 사용자가 입력을 멈추면 마지막에 발생한 이벤트 하나만 실행시킨다. 

<iframe src="https://codesandbox.io/embed/dibaunseu-keypress-qb62ug?fontsize=14&hidenavigation=1&theme=dark"
     style="width:100%; height:400px; border:0; border-radius: 4px; overflow:hidden;"
     title="디바운스 - keyPress"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>

<br />

```js
// ✨ debounce (실행시킬 함수, delay 시간)

const debounce = (callback, delay = 1000) => {
  let timer;
  return () => {
    setHandleLoading(true);
    // 실행 함수 setTime out 취소
    clearTimeout(timer);

    //delay만큼 시간이 지나면  callback 함수 실행
    timer = setTimeout(() => {
      return callback();
    }, delay);
  };
};

```

<br />
<br />
<br />

## 스로틀(Throttle)

스로틀은 일정 주기마다 이벤트를 발생시킨다.
마지막 함수 실행 후 일정 시간이 지나야만 호출이되는 기술이다.
- 예) 무한 스크롤을 구현할때 

<iframe src="https://codesandbox.io/embed/throttle-muhanseukeurol-j1xmu7?fontsize=14&hidenavigation=1&theme=dark"
     style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;"
     title=" Throttle - 무한스크롤"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>

<br />

```js
// ✨ throttle
// throttle(실행시킬 함수, delay시간)
const throttle = (callback, delay = 400) => {
  let timer = null;
  return (e) => {
    if (timer === null) {
      timer = setTimeout(() => {
        callback(e);
        timer = null;
      }, delay);
    }
  };
};
```
   
<br /><br /><br /><br />

**< Refer to >**  
<https://webclub.tistory.com/607>