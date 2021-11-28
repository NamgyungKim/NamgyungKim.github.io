---
title: "[Python] 크롤링"
layout: single
categories: Python
tag: [크롤링, python]
---

## 기본 세팅
```python
import requests
from bs4 import BeautifulSoup

headers = {'User-Agent' : 'Mozilla/5.0 (Windows NT 10.0; Win64; x64)AppleWebKit/537.36 (KHTML, like Gecko) Chrome/73.0.3683.86 Safari/537.36'}
data = requests.get('크롤링할 페이지 URL',headers=headers)

soup = BeautifulSoup(data.text, 'html.parser') 
# soup: 웹문서 전체

# ----- 이후 코딩 ----- #
# ( 예제 )
movies = soup.select('#old_content > table > tbody > tr')
# selector복사
for movie in movies:
    a_tag = movie.select_one('td.title > div > a')
    if a_tag is not None:
        print (a_tag.text)
```
<br />

## 태그 가져오기
```html
<meta id="meta" content="contents...." name="name..." />
<body>
  ...
  <h1 id="title">제목</h1>
  ...
</body>
```
위 html에서 content가져오기
```python
print(movie.select_one('#meta')['content'])
# contents....
```
위 html에서 h1 텍스트 가져오기
```python
print(movie.select_one('#title').text)
# 제목
```

<br />
<br />
<br />
<br />
