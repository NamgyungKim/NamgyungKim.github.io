---
title: "[Python] Flask-기초"
layout: single
categories: Python
tag: [python, flask]
---

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/2021-10-16-Flask/Flask_logo.png" alt="flask_logo" style="width:80%; display: block; margin: 50px auto">

## Flask란

**Flask**은 Django, FaskAPI와 같이 대표적인 **Python 프레임워크** 중 하나이다.

- Flask는 장고에 비해 배우기 쉽다.
- 적은 코드라인으로 앱 구축이 가능하다.
- 라이브러리를 자유롭게 사용하여, 응용 프로그램을 빠르게 확장할 수 있는 유연성을 제공한다.
  그러므로 단일 기능 또는 어드민이 필요없는 소규모 프로젝트에 쓰기에 좋다.

**++추가** <br />
Django: 여러 기능이 복합적으로 구성되어 있거나, 백오피스 기능이 필요한 경우 적합.<br />
FastAPI: API 서버, 마이크로 서비스, 빠른 개발이 필요한 백엔드 프로젝트의 경우 적합.<br />

## 시작하기

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run('0.0.0.0',port=5000,debug=True)
    # http://localhost:5000/ 에서 실행
```

### Route

http://localhost:5000/home, http://localhost:5000/user 페이지 생성

```python
@app.route('/')
@app.route('/home')
def home():
    return 'Home'
@app.route('/user')
def user():
    return 'User'
```

### HTML랜더링

```python
from flask import Flask, render_template

@app.route('/')
def home():
  return render_template('index.html')
# template폴더에 index.html이 return됨.
```

<br />
<br />
<br />
<br />
