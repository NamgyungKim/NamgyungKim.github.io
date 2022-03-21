---
title: "[JS] 배열 함수 정리"
sidebar_main: true
layout: single
categories: 
  - JavaScript  
tag: [배열함수]
toc: true #true/ false
toc_sticky: true
---

![호이스팅이란?]({{ site.url }}{{ site.baseurl }}/assets/images/2022/03/21.png)

<br />

# 배열 함수 정리

js 에서의 배열을 일반적인 배열의 동작을 흉내낸 객체(Object)이다. 

<br />

## 배열 함수

### 배열 생성 함수
```js
const arr1 = []
const arr2 = new Array()
const arr3 = new Array(3) // []
const arr4 = new Array(5).fill(1) // [1,1,1,1,1]
const arr5 = Array.from(Array(5), function(v, i){
  return i+1
}) // [1,2,3,4,5]
```
- 배열.fill(x)  
  배열 전체를 x로 변경  
- Array.from 함수  
  Array.from('초기화할 배열',function(배열의 값,배열의 index){return})

<br/>
<br/>

### join

- 배열의 각 값들을 합쳐주는 함수

```js
const arr = [1,2,3,4,5,6]
arr.join('/') // 1/2/3/4/5/6
```

<br/>
<br/>

### reverse

🚨 원본 배열이 바뀜 주의해서 사용!
- 배열을 뒤집어주는 함수  

```js
const arr = [1,2,3,4,5]
arr.reverse() // [5,4,3,2,1]
```

<br/>
<br/>

### concat

- 두 배열을 합치는 함수

```js
const arr1 = [1,2,3]
const arr2 = [4,5,6]
arr1.concat(arr2) // [1,2,3,4,5,6]
```

<br/>
<br/>

### push, pop, shift, unshift

🚨 원본 배열이 바뀜 주의해서 사용!
- push(x): 배열 뒤에 x를 추가
- pop(): 배열 가장 마지막 값을 제거
- unshift(x): 배열 맨 앞에 x 추가
- shift(): 배열 맨 앞의 값 제거

<br/>
<br/>

### slice

- slice(x,y): 배열의 중간 값을 가져온다.
  원본배열을 바꾸지 않는다.
  index x에서부터 y까지를 가져온다.  

```js
const arr = [1,2,3,4,5]
arr1.slice(2,4) // [3,4]
```

<br/>
<br/>

###  splice

🚨 원본 배열이 바뀜 주의해서 사용!
- splice(x,y): 배열의 중간 값을 제거
  index x부터 시작해서 갯수y개를 제거

```js
const arr2 = [1,2,3,4,5]
arr2.splice(1,2) // [1,4,5]
```

<br/>
<br/>

## 배열의 순회

### for... of
```js
for(const item of arr){
  console.log(item) // 1 ~ 5 까지 순서대로 찍힌다.
}
```

<br/>

### forEach

```js
arr.for((item,index)=>{})
```

<br/>

### map

배열을 return 한다.

```js
const data = arr.map((item,index) => {return ...})
```

<br/>

### filter

조건문에 맞는 item만 배열로 반환 한다.

```js
const data = arr.filter((item,index) => {return (true/false 조건문)})
```

<br/>

### some

조건에 맞는 데이터가 있는지여부를 boolean으로 반환 한다.

```js
const data = arr.some((item,index) => {return (조건)})
```

<br/><br/><br/><br/>