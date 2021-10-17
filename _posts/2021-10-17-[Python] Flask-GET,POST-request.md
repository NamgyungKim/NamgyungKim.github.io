---
title: "[Python] Flask-GET,POST요청"
layout: single
categories: Python
tag: [python, flask, mongoDB]
---

## Post

```js
// index.html 폴더

function makeReview() {
  // 1. html <from></from>태그 안의 val 값 가져오기
  let title = $("#title").val();
  let author = $("#author").val();
  let review = $("#bookReview").val();

  $.ajax({
    type: "POST",
    url: "/review",
    data: {
      // 2. 가져온 데이터를 app.py의 ..._receive 에 넣기
      title_give: title,
      author_give: author,
      review_give: review,
    },
    success: function (response) {
      // 7. 성공시, 알림창에 msg(app.py의 msg값)띄우기
      alert(response["msg"]);
      // 8. 페이지 리로딩
      window.location.reload();
    },
  });
}

<form>...</form>;
```

```python
# app.py 폴더

from flask import Flask, request, jsonify

# mongo db 연결
from pymongo import MongoClient
client = MongoClient('localhost', 27017)
db = client.dbsparta

@app.route('/review', methods=['POST'])
def write_review():
    # 3. ..._give 에서 받어온 데이터 ..._receive에 넣기
    title_receive = request.form['title_give']
    author_receive = request.form['author_give']
    review_receive = request.form['review_give']

    doc = {
      # 4. field에 value 매치
        'title': title_receive,
        'author': author_receive,
        'review': review_receive
    }

    db.bookreview.insert_one(doc) # 5.db에 입력

    # 6.db에 저장 후 msg return
    return jsonify({'msg': '저장 완료'})
```

## GET

```js
// index.html 폴더

function showReview() {
  $.ajax({
    type: "GET",
    url: "/review",
    data: {},
    success: function (response) {
      //3. all_reviews값 reviews에 받아오기
      let reviews = response["all_reviews"];
      for (let i = 0; i < reviews.length; i++) {
        //4. html에 데이터 입력
        let title = reviews[i]["title"];
        let author = reviews[i]["author"];
        let review = reviews[i]["review"];

        let temp_html = `<tr>
                <td>${title}</td>
                <td>${author}</td>
                <td>${review}</td>
              </tr>`;

        $("#reviews-box").append(temp_html);
      }
    },
  });
}

<form>...</form>;
```

```python
# app.py 폴더

from flask import Flask, jsonify

# mongo db 연결
from pymongo import MongoClient
client = MongoClient('localhost', 27017)
db = client.dbsparta

@app.route('/review', methods=['GET'])
def read_reviews():
    #1. bookreview안의 모든 데이터 reviews에 넣기
    reviews = list(db.bookreview.find({},{'_id':False}))
    #2. revies값을 all_reviews에 담아서 return
    return jsonify({'all_reviews': reviews})
```

<br />
<br />
<br />
<br />
