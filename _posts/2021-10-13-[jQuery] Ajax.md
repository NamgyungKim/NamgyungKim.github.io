---
title: "[jQuery] Ajax사용법"
layout: single
categories: jQuery
tag: [Ajax, jQuery]
---



## Ajax 기본 골격

```js
$.ajax({
  type:      
  url :       
  data:       
  dataType:   
  success: function(result){ 
  },
  error:function(){ 
  }
})
```

## 매개변수

||  매개변수  | | | 설명|
|--| :----------: | --  | -- | -------------------------------------------------------------------- |
|| type ||| 데이터 전송 타입 (GET or POST) |
|| url ||| 데이터를 주고받을 파일 주소 입력 |
|| data ||| 서버로 보낼 데이터 지정(GET요청시 비워두기) |
|| dataType ||| 데이터의 타입 (생략가능) |
|| success() ||| 작업이 성공적으로 발생했을 경우 실행시킬 함수 (result, status, xhr) |
|| error() ||| 요청이 실패할 경우 실행시킬 함수(xhr, status,error) |
||   async   ||| true: 비동기로 처리(기본값)  false:동기로 처리 |
||   beforeSend()   ||| 요청을 보내기 전에 실행할 함수 |
||  complete()  ||| 요청 완료 시 실행할 함수 |
|| password ||| HTTP 액세스 인증 요청에 사용할 암호 지정 |
|| username ||| HTTP엑세스 인증 요청에 사용할 사용자 이름 지정 |
|| timeout ||| 요청에 대한 로컬 제한 시간 (ms) |


<br />
<br />
<br />
<br />

**< Refer to >**<br />

[[AJAX] JQ - $.ajax() 메서드](https://homzzang.com/b/jquery-247)
