---
title: "Warning:&#12296;p&#12297;cannot appear as a descendant of&#12296;p&#12297;"
sidebar_main: true
layout: single
categories: 
  - errorHandling  
tag: [error]
---

![애러]({{ site.url }}{{ site.baseurl }}/assets/images/2022/03/27.jpg)

<br />
react에서 p태그 안에 p태그를 작성했더니 저런 경고메시지가 콘솔에 찍혔다.  
그냥 html에 찍었을 때는 저런 경고창이 뜨지는 않았다.  
p태그 안에있는 p를 span 태그로 바꾸어주었더니 경고메시지가 사라졌다.  

<br/>

# p태그 안에 p태그 작성
HTML에서 p태그의 p는 paragraph(문단)의 약자 이다.  
그래서 p태그는 여러 줄의 글을 나타낼때 사용된다.  
그런데 그런 p태그를 안에 중첩해서 사용하게되면, 혹은 안에 div처럼 block 태그를 사용하게되면 랜더링 시에 p태그 밖으로 밀려나오게 된다.  
```html
<p>p태그 속의 <p>p태그</p> <div>div태그</div> </p>
```
![애러]({{ site.url }}{{ site.baseurl }}/assets/images/2022/03/27_1.jpg)

그렇기 때문에 span태그나 a, em 같은 inline태그를 넣어주어야한다. 



<br/><br/><br/><br/>

**< Refer to >**  

<https://blogpack.tistory.com/996>