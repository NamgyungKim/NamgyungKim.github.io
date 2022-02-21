---
title: "마크다운(Marckdown) 문법 정리"
layout: single
sidebar_main: true
categories: 
  - etc
tag: [Marckdown]
toc: true #true/ false
toc_sticky: true
---

# 마크다운 이란?

존 그루버가 만든 마크다운(Markdown) 은 읽기 쉽고 쓰기 쉽게 만들어진 일반 텍스트 작성 문법으로, 사용법이 간단해서 누구나 쉽게 배울 수 있고, 빠르게 글을 쓸 수 있습니다. 또한 html 태그 구조를 아는 분이라면, 더욱 쉽게 사용할 수 있습니다.

![이미지]({{ site.url }}{{ site.baseurl }}/assets/images/2022/02/18.jpg)

VScode같은 경우 오른쪽 상단의 돋보기 버튼 클릭 시 미리 보기를 할 수 있다.

<br />
<br />


# 문법 (Syntex) 
( 아래 마크다운 문법에 따른 스타일은 각 웹사이트의 별로 다를 수 있습니다. )

## 1. 제목 

```md
# h1
## h2
### h3
#### h4
##### h5
###### h6
```
<br />


## 2. 인용문 

```md
> 첫번째 인용문
>> 두번째 인용문
>>> 세번째 인용문
```

> 첫번째 인용문
>> 두번째 인용문
>>> 세번째 인용문

<br />

## 3. 목록

### 순서가 있는 경우
```md
1. 첫번째
   1. 하위
   2. 하위
2. 두번째
3. 세번째
```
1. 첫번째
   1. 하위
   2. 하위
2. 두번째
3. 세번째

### 순서가 없는 경우
```md
+ 목록
   - 하위목록
   - 하위목록
      - 하위목록
+ 목록
+ 목록
- 목록
```

+ 목록
   - 하위목록
   - 하위목록
      - 하위목록
+ 목록
+ 목록
- 목록

<br />

## 링크
```md
[링크 이름](https://www.google.com/)
 <namgyung.kim@gmail.com>
```
  [링크 이름](https://www.google.com/) 

 <namgyung.kim@gmail.com>

 <br />

## 이미지
```md
![이미지 텍스트](https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png)

이미지에 링크  
[![이미지 텍스트](https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png)](https://www.google.com/)

```
![이미지 텍스트](https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png)

이미지에 링크  
[![이미지 텍스트](https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png)](https://www.google.com/)

<br />

## 강조
```md
_이텔릭체_
__볼드체__
**볼드체**
***볼드체+이텔릭체***
___볼드체+이텔릭체___
~~취소선~~
**~~볼드체+취소선~~**
<u>밑줄</u>
``` 
_이텔릭체_ 

__볼드체__

**볼드체**

***볼드체+이텔릭체***

___볼드체+이텔릭체___

~~취소선~~

**~~볼드체+취소선~~**

<u>밑줄</u>

<br />

## 코드
```md
  ```js
   console.log(123)
   const func = () => {
    console.log('func')
   }
  ``` (js 언어)

  ```html
   <h1>제목</h1>
   <div id="section">...</div>
  ``` (html언어)
```

  ```js
   console.log(123)
   const func = () => {
    console.log('func')
   }
  ``` 

  ```html
   <h1>제목</h1>
   <div id="section">...</div>
  ``` 
<br />

## 수평선
```md
구분선 1
---
구분선 2
***
구분선 3
___
```
구분선 1

---
구분선 2

***
구분선 3

___

<br />

## 표
```md
|기본 정렬|가운데 정렬|우측정렬|
|---|:---:|---:|
|ㅁ----------------------|-----------ㅁ---------|----------------------ㅁ|
|abc|1234567|abc|
|abc|1234567|abc|
```
|기본 정렬|가운데 정렬|우측정렬|
|---|:---:|---:|
|ㅁ----------------------|-----------ㅁ---------|----------------------ㅁ|
|abc|1234567|abc|
|abc|1234567|abc|

<br />

## 줄바꿈
```md
ABCDEF<br />GHIJKLM(뒤에 스페이스바2번 후 엔터)  
NOPQRSTUVWXYZ
```
ABCDEF<br />GHIJKLM(뒤에 스페이스바2번 후 엔터)  
NOPQRSTUVWXYZ




<br /><br /><br /><br />

**< Refer to >**  
[MarkDown 사용법 총정리](https://heropy.blog/2017/09/30/markdown/)

