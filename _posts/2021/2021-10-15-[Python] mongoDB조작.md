---
title: "[Python] mongoDB조작"
layout: single
categories: Python
tag: [python, mongoDB]
---

## 시작하기
```python
from pymongo import MongoClient           # pymongo를 import 하기
client = MongoClient('localhost', 27017)  # mongoDB는 27017 포트로 돌아갑니다.
db = client.dbname                        # 'dbname'라는 이름의 db를 만듭니다.
```

### MongoDB에 데이터 넣기
```python
# 'users'라는 collection에 {'name':'bobby','age':21}를 넣습니다.
db.users.insert_one({'name':'bobby','age':21})
db.users.insert_one({'name':'kay','age':27})
db.users.insert_one({'name':'john','age':30})
```

### 데이터 값 보기
```python
# MongoDB에서 데이터 모두 보기
all_users = list(db.users.find({}))
# MongoDB에서 특정 조건의 데이터 모두 보기
same_ages = list(db.users.find({'age':21},{'_id':False}))
# 특정 결과값 뽑아보기
user = db.users.find_one({'name':'bobby'})
```

### 데이터 수정
```python
# db.users.update_one({ 찾을 조건 },{'$set':{ 어떻게 바꿀지 }})
db.users.update_one({'name':'bobby'},{'$set':{'age':19}})
```

### 삭제하기
```python
db.users.delete_one({'name':'bobby'})
```



<br />
<br />
<br />
<br />