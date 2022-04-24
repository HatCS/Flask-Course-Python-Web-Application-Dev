# Flask Course - Python Web Application Development

https://www.youtube.com/watch?v=Qr4QMBUPxWo

Useful Links:
🔗 Python Download - https://www.python.org/downloads/​
🔗 Pycharm Download - https://www.jetbrains.com/pycharm/dow...
🔗 Flask Starter Template - https://flask.palletsprojects.com/en/2.1.x/...

💻 Full code: https://github.com/jimdevops19/codesnippets
💻 Get code snippets used in the course: http://www.jimshapedcoding.com/

✏️ Course created by Jim from JimShapedCoding. Check out his channel: https://www.youtube.com/channel/UCU8d7rcShA7MGuDyYH1aWGg


⭐️ Course Contents ⭐️
## ⌨️ P1 Introduction

Program install:

OS Ubuntu 20.04;
Python 3.8;
PyCharm;

$ sudo apt install python3-pip

 pip install flask
 
 ![](https://i.imgur.com/uR4NriN.png)

Установим (экспортируем) переменные среды

export FLASK_APP=market.py

Запустим в терминале`flask run`

Включим режим отладки:
/FlaskMarket$ export FLASK_DEBUG=1

Для изменения и синхронизации кода и браузера

![](https://i.imgur.com/XICLLCB.png)

## ⌨️ P2  (0:20:37) Styling & Templates

Create new directory `templates` and html-file home in templates

![](https://i.imgur.com/10KPQu9.png)


Используем фреймворк стилей Bootstrap

Скопируем с раздела Starter template https://getbootstrap.com/docs/5.1/getting-started/introduction/
и вставим в home.html
```

<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
 </body>
</html>
```



![](https://i.imgur.com/XaKx6Ox.png)

![](https://i.imgur.com/yXaOvxZ.png)

![](https://i.imgur.com/1wsolaT.png)



## ⌨️ P3  (0:41:37) Sending data to Templates

Create new route

![](https://i.imgur.com/tGp1UX8.png)

Create file market.html in directory templates:

![](https://i.imgur.com/QY1msw0.png)

![](https://i.imgur.com/xjGnYKe.png)

Copy items_list_for_dictionaries in market.py

```
items = [
    {'id': 1, 'name': 'Phone', 'barcode': '893212299897', 'price': 500},
    {'id': 2, 'name': 'Laptop', 'barcode': '123985473165', 'price': 900},
    {'id': 3, 'name': 'Keyboard', 'barcode': '231985128446', 'price': 150}
]
```

![](https://i.imgur.com/vkfOTls.png)


![](https://i.imgur.com/6yaEV7B.png)


![](https://i.imgur.com/JCnLhd5.png)



![](https://i.imgur.com/7YDKYqK.png)


Add two button:

![](https://i.imgur.com/AkoglIn.png)


![](https://i.imgur.com/JRBmDR7.png)

## ⌨️ P4  (1:02:56) Template Inheritance

Create html file base.html in templates 
```
<!doctype html>
<html lang="en">
   <head>
      <!-- Required meta tags -->
      <meta charset="utf-8">
      <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
      <!-- Bootstrap CSS -->
      <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
      <title>Base Title</title>
   </head>
   <body>
      <script src='https://kit.fontawesome.com/a076d05399.js'></script>
      <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
      <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js" integrity="sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN" crossorigin="anonymous"></script>
      <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js" integrity="sha384-B4gt1jrGC7Jh4AgTPSdUtOBvfO8shuf57BaghqFfPlYxofvL8/KUEfYiJOMMV+rV" crossorigin="anonymous"></script>
   </body>
   <style>
      body {
      background-color: #212121;
      color: white
      }
   </style>
</html>
```

Delete in Home.html code and add: 
`{% extends 'base.html' %}`


Add in base.html:
```
 <nav class="navbar navbar-expand-md navbar-dark bg-dark">
      <a class="navbar-brand" href="#">Flask Market</a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav mr-auto">
            <li class="nav-item active">
              <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Market</a>
            </li>
        </ul>
        <ul class="navbar-nav">
            <li class="nav-item1">
                <a class="nav-link" href="#">Login</a>
           </li>
           <li class="nav-item2">
                <a class="nav-link" href="#">Register</a>
            </li>
        </ul>
      </div>
    </nav>
```


![](https://i.imgur.com/OPlzcLd.png)


![](https://i.imgur.com/2ditX9p.png)


Code in market.html:

```
{% extends 'base.html' %}

{% block title %}
    Market Page
{% endblock %}

{% block content %}
<table class="table table-hover table-dark">
        <thead>
            <tr>
                <!-- Your Columns HERE -->
                <th scope="col">ID</th>
                <th scope="col">Name</th>
                <th scope="col">Barcode</th>
                <th scope="col">Price</th>
                <th scope="col">Options</th>
            </tr>
        </thead>
        <tbody>
            <!-- Your rows inside the table HERE: -->
            {% for item in items %}
                <tr>
                     <td> {{ item.id }} </td>
                     <td> {{ item.name }} </td>
                     <td> {{ item.barcode }} </td>
                     <td> {{ item.price }} $</td>
                     <td>
                         <button class="btn btn-outline btn-info">More info</button>
                         <button class="btn btn-outline btn-success">Purchase this Item</button>
                     </td>
                </tr>
            {% endfor %}

        </tbody>
    </table>
{% endblock %}
```

Make redirecting in other pages:

![](https://i.imgur.com/t9gvfC3.png)


![](https://i.imgur.com/IqpzOX4.png)




## ⌨️ P5  (1:21:14) Models and Databases


`~/FlaskMarket$ pip install flask-sqlalchemy`



![](https://i.imgur.com/9R8ehNU.png)


![](https://i.imgur.com/6MwACY6.png)

Импортируем базу данных в проект 

`/FlaskMarket$ python3`

```
>>> from market import db
/home/osboxes/.local/lib/python3.8/site-packages/flask_sqlalchemy/__init__.py:872: FSADeprecationWarning: SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and will be disabled by default in the future.  Set it to True or False to suppress this warning.
  warnings.warn(FSADeprecationWarning(
>>> 
```

`>>> db.create_all()`

```
>>> from market import Item
>>> item1 = Item(name="IPhone 10", price=500, barcode='1234567890123',description='desc')
```
```
>>> Item.query.all()
[<Item 1>]
>>> item1 = Item(name="Laptop", price=700, barcode='098765432109',description='esc')
>>> item2 = Item(name="Laptop", price=700, barcode='098765432109',description='esc')
>>> db.session.add(item2)
>>> db.session.commit()
>>> Item.query.all()
[<Item 1>, <Item 2>]
```

![](https://i.imgur.com/vTuzn1t.png)

 ```
python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) 
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from market import db
/home/osboxes/.local/lib/python3.8/site-packages/flask_sqlalchemy/__init__.py:872: FSADeprecationWarning: SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and will be disabled by default in the future.  Set it to True or False to suppress this warning.
  warnings.warn(FSADeprecationWarning(
>>> from market import Item
```

```
>>> from market import Item
>>> Item.query.all()
[Item IPhone 10, Item Laptop]
```

```
>>> for item in Item.query.all():
...  item.name
...  item.price
...  item.description
...  item.id
...  item.barcode
... 
'IPhone 10'
500
'desc'
1
'1234567890123'
'Laptop'
700
'esc'
2
'098765432109'
>>> 
```
```
>>> Item.query.filter_by(price=500)
<flask_sqlalchemy.BaseQuery object at 0x7f9596da05b0>
>>> for item in Item.query.filter_by(price=500):
...  item.name
... 
'IPhone 10'
```

![](https://i.imgur.com/6TATVMC.png)

```
osboxes@osboxes:~/FlaskMarket$ export FLASK_APP=market.py
osboxes@osboxes:~/FlaskMarket$ export FLASK_DEBUG=1
osboxes@osboxes:~/FlaskMarket$ flask run
```

Для просмотра БД используем sqlite browser
osboxes@osboxes:~/FlaskMarket$  snap install sqlitebrowser


![](https://i.imgur.com/6IeKVVg.png)

## ⌨️ P6  (1:51:13) Project Restructure

С файла market.py вырежим 

```
class Item(db.Model):
    id = db.Column(db.Integer(), primary_key=True)
    name = db.Column(db.String(length=30), nullable=False, unique=True)
    price = db.Column(db.Integer(), nullable=False)
    barcode = db.Column(db.String(length=12), nullable=False, unique=True)
    description = db.Column(db.String(length=1024), nullable=False, unique=True)

    def __repr__(self):
        return f'Item {self.name}'```
```
        
и перенсем в новь созданный файл model.py

С файла market.py вырежим 
```
@app.route("/")
@app.route('/home')
def home_page():
    return render_template('Home.html')
@app.route('/market')
def market_page():
    items = Item.query.all()
    return render_template('market.html', items=items)
```
и перенсем в новь созданный файл routes.py

Create file run.py
copy with market.py all code in run.py

delete market.py

![](https://i.imgur.com/TIG5FLX.png)


![](https://i.imgur.com/gtr7qEU.png)

Copy code with run.py in __init__

```
from flask import Flask, render_template
from flask_sqlalchemy import SQLAlchemy

app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///market.db'
db = SQLAlchemy(app)
```


![](https://i.imgur.com/N524QF1.png)


~/FlaskMarket$ python3 run.py 


![](https://i.imgur.com/WWkPDIU.png)


![](https://i.imgur.com/p7i7B4g.png)


![](https://i.imgur.com/NraSvy3.png)


:~/FlaskMarket$ python3 run.py 




## ⌨️ P7  (2:05:41) Model Relationships

![](https://i.imgur.com/UtOFeEF.png)


```
class User(db.Model):
    id = db.Column(db.Integer(), primary_key=True)
    username = db.Column(db.String(length=30), nullable=False, unique=True)
    email_address = db.Column(db.String(length=50), nullable=False, unique=True)
    password_hash = db.Column(db.String(length=60), nullable=False)
    budget = db.Column(db.Integer(),nullable=False, default=1000)
    items = db.relationship('Item', backref='owned_user', lazy=True)
    

class Item(db.Model):
    id = db.Column(db.Integer(), primary_key=True)
    name = db.Column(db.String(length=30), nullable=False, unique=True)
    price = db.Column(db.Integer(), nullable=False)
    barcode = db.Column(db.String(length=12), nullable=False, unique=True)
    description = db.Column(db.String(length=1024), nullable=False, unique=True)
    owner = db.Column(db.Integer(), db.ForeignKey('user.id'))
```

```
>>> from market.models import db
/home/osboxes/.local/lib/python3.8/site-packages/flask_sqlalchemy/__init__.py:872: FSADeprecationWarning: SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and will be disabled by default in the future.  Set it to True or False to suppress this warning.
  warnings.warn(FSADeprecationWarning(
>>> db.drop_all()
>>> db.create_all()
>>> from market.models import User,Item
>>> u1 = User(username='jsc', password_hash='12345678', email_address='jsc@jsc.com')
>>> import os
>>> os.system('clear')
>>> db.session.add(u1)
>>> db.session.commit()
>>> User.query.all()
[<User 1>]
>>> i1=Item(name='Iphone 10', description='description',barcode='1234567890123',price=800)
>>> db.session.add(i1)
>>> db.session.commit()
>>> i2=Item(name='Laptop', description='description2',barcode='876543210123',price=1000)
>>> db.session.add(i2)
>>> db.session.commit()
>>> i2=Item(name='Laptop', description='description2',barcode='876543210123',price=1000)
>>> db.session.add(i2)
>>> db.session.commit()
>>> Item.query.all()
[Item Iphone 10, Item Laptop]
>>> item1=Item.query.filter_by(name='Iphone 10')
>>> item1
<flask_sqlalchemy.BaseQuery object at 0x7fb83075c9a0>
>>> item1=Item.query.filter_by(name='Iphone 10').first()
>>> item1
Item Iphone 10
>>> item1.owner
>>> item1.owner = User.query.filter_by(username='jsc').first()
>>> db.session.add(item1)
>>> db.session.commit()
>>> db.session.rollback()
>>> item1.owner = User.query.filter_by(username='jsc').first().id
>>> db.session.add()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: add() missing 1 required positional argument: 'instance'
>>> db.session.add(item1)
>>> db.session.commit()
>>> item1.owner
1
>>> i = Item.query.filtert()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'BaseQuery' object has no attribute 'filtert'
>>> i = Item.query.filtert_by(name='Iphone 10')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'BaseQuery' object has no attribute 'filtert_by'
>>> i = Item.query.filter_by(name='Iphone 10')
>>> i = Item.query.filter_by(name='Iphone 10').first()
>>> i.woned_user
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Item' object has no attribute 'woned_user'
>>> i.owned_user
<User 1>


```


## ⌨️ P8  (2:25:37) Flask Forms
```

~/FlaskMarket$ pip install flask-wtf
~/FlaskMarket$ pip install wtforms

```
Create forms.py in directory market

![](https://i.imgur.com/B0odIKE.png)


![](https://i.imgur.com/vIYveUa.png)

![](https://i.imgur.com/fSZgA9P.png)

![](https://i.imgur.com/P9hAGhk.png)

![](https://i.imgur.com/fzMW9d6.png)


![](https://i.imgur.com/Yeyxwuv.png)

![](https://i.imgur.com/S9xqlA2.png)


![](https://i.imgur.com/A3thfrY.png)


![](https://i.imgur.com/ApkQccq.png)

![](https://i.imgur.com/NzX1SBc.png)


![](https://i.imgur.com/G65eI98.png)


## ⌨️ P9  (2:51:58) Flask Validations

```
In file routes.py write code:

from market import app
from flask import render_template, redirect,url_for
from market.models import Item, User
from market.forms import RegisterForm
from market import db

@app.route("/")
@app.route('/home')
def home_page():
    return render_template('Home.html')
@app.route('/market')
def market_page():
    items = Item.query.all()
    return render_template('market.html', items=items)

@app.route('/register', methods=['GET', 'POST'])
def register_page():
    form = RegisterForm()
    if form.validate_on_submit():
        user_to_create = User(username=form.username.data,
                              email_address=form.email_address.data,
                              password_hash=form.password1.data)
        db.session.add(user_to_create)
        db.session.commit()
        return redirect(url_for('market_page'))

    return render_template('register.html',form=form)
```

![](https://i.imgur.com/0zD6dbw.png)


![](https://i.imgur.com/vZ5pL0i.png)


![](https://i.imgur.com/vtCErlW.png)


`osboxes@osboxes:~/FlaskMarket$ pip install email_validator`


## ⌨️ P10 (3:14:05) Flashes & Advanced Validations


![](https://i.imgur.com/8iUjh6K.png)


![](https://i.imgur.com/rZrgRwu.png)



![](https://i.imgur.com/G0j08WM.png)


![](https://i.imgur.com/bolOWbI.png)


![](https://i.imgur.com/PZ5sl0x.png)

![](https://i.imgur.com/v0DwPTX.png)

![](https://i.imgur.com/LudMUBz.png)


![](https://i.imgur.com/E5CEx2k.png)


![](https://i.imgur.com/g0lkMHr.png)


![](https://i.imgur.com/jrhV24J.png)


![](https://i.imgur.com/6uQozcJ.png)


![](https://i.imgur.com/m1k1xYH.png)



## ⌨️ P11 (3:41:04) User Authentication Part 1

In terminal write:

` pip install flask_bcrypt`


![](https://i.imgur.com/6pydX3C.png)


![](https://i.imgur.com/8SjV5Nr.png)


![](https://i.imgur.com/nXT1bCH.png)


![](https://i.imgur.com/Nw3EoMz.png)



Create new file login.html


![](https://i.imgur.com/EGV844Z.png)


![](https://i.imgur.com/tOMbVdI.png)


![](https://i.imgur.com/vLGaoYt.png)


![](https://i.imgur.com/jP4uK3p.png)


![](https://i.imgur.com/kQI4Za7.png)


![](https://i.imgur.com/LqM7RDW.png)



![](https://i.imgur.com/LcpcryT.png)


![](https://i.imgur.com/3uplqap.png)



## ⌨️ P12 (3:59:56) User Authentication Part 2

`$ pip install flask_login`


![](https://i.imgur.com/ss4GnSR.png)


![](https://i.imgur.com/A07IjIz.png)


![](https://i.imgur.com/OqaxOnR.png)


![](https://i.imgur.com/MDy133o.png)


![](https://i.imgur.com/yDvOZNs.png)


![](https://i.imgur.com/LhjQpKz.png)


![](https://i.imgur.com/cXoxvf6.png)


![](https://i.imgur.com/ACN4kFE.png)


![](https://i.imgur.com/P748wMV.png)


![](https://i.imgur.com/TJL04bo.png)


![](https://i.imgur.com/T6ECS8q.png)


![](https://i.imgur.com/da9Atx7.png)


![](https://i.imgur.com/YDQJ3R2.png)


![](https://i.imgur.com/w6DkCLy.png)


![](https://i.imgur.com/C0ubk3r.png)


![](https://i.imgur.com/Gq0HTdY.png)



## ⌨️ P13 (4:34:16) Logout and Customizations



![](https://i.imgur.com/sk1eqSY.png)


![](https://i.imgur.com/nX0Eck2.png)


![](https://i.imgur.com/S0dqK8w.png)


![](https://i.imgur.com/ESmFDUJ.png)


![](https://i.imgur.com/3y7tv4a.png)


![](https://i.imgur.com/B5TKvcC.png)


![](https://i.imgur.com/rKPPlf3.png)


![](https://i.imgur.com/XaHDmRn.png)


![](https://i.imgur.com/x38PjJE.png)


![](https://i.imgur.com/wTpJ2sr.png)


![](https://i.imgur.com/kvb6ToF.png)


![](https://i.imgur.com/WvwWZED.png)


## ⌨️ P14 (4:51:25) Item Purchasing Part 1

Add change market.html:

```
{% extends 'base.html' %}
{% block title %}
    Market Page
{% endblock %}

{% block content %}
  <div class="row">
    <div class="col-8">
         <table class="table table-hover table-dark">
        <thead>
            <tr>
                <!-- Your Columns HERE -->
                <th scope="col">ID</th>
                <th scope="col">Name</th>
                <th scope="col">Barcode</th>
                <th scope="col">Price</th>
                <th scope="col">Options</th>
            </tr>
        </thead>
        <tbody>
            <!-- Your rows inside the table HERE: -->
            {% for item in items %}
                <tr>
                     <td> {{ item.id }} </td>
                     <td> {{ item.name }} </td>
                     <td> {{ item.barcode }} </td>
                     <td> {{ item.price }} $</td>
                     <td>
                         <button class="btn btn-outline btn-info">More info</button>
                         <button class="btn btn-outline btn-success">Purchase this Item</button>
                     </td>
                </tr>
            {% endfor %}

        </tbody>
    </table>
    </div>
    <div class="col-4">col-4</div>
  </div>

{% endblock %}




```

```
{% extends 'base.html' %}
{% block title %}
Market Page
{% endblock %}
{% block content %}
<div class="row" style="margin-top: 20px; margin-left: 20px">
   <div class="col-8">
       <h2>Available Items on the Market</h2>
       <p>Click on one of the itmes to start buying</p>
       <br>
      <table class="table table-hover table-dark">
         <thead>
            <tr>
               <!-- Your Columns HERE -->
               <th scope="col">ID</th>
               <th scope="col">Name</th>
               <th scope="col">Barcode</th>
               <th scope="col">Price</th>
               <th scope="col">Options</th>
            </tr>
         </thead>
         <tbody>
            <!-- Your rows inside the table HERE: -->
            {% for item in items %}
            <tr>
               <td> {{ item.id }} </td>
               <td> {{ item.name }} </td>
               <td> {{ item.barcode }} </td>
               <td> {{ item.price }} $</td>
               <td>
                  <button class="btn btn-outline btn-info">More info</button>
                  <button class="btn btn-outline btn-success">Purchase this Item</button>
               </td>
            </tr>
            {% endfor %}
         </tbody>
      </table>
   </div>
   <div class="col-4">
        <h2>Owned Items</h2>
        <p>Click on sell item to put an item back on the Market</p>
        <br>
   </div>
</div>
{% endblock %}
```

Create new directory : `includes`

Create new file: items_modals.html

```
<style>
  .modal-content {
    background-color: #212121
  }
</style>

<!-- More Info -->
<div class="modal fade" id="Modal-MoreInfo-{{ item.id }}"
     tabindex="-1"
     aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="ModalLabel">
          <!-- -->
          {{ item.name }}
        </h5>
        <button type="button" class="close"
                data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        {{ item.description }}
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary"
                data-dismiss="modal">Close
        </button>
      </div>
    </div>
  </div>
</div>

<!-- Purchase Confirm -->
<div class="modal fade" id="Modal-PurchaseConfirm-{{ item.id }}"
     tabindex="-1"
     aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="ModalLabel">
          <!-- -->
          {{ item.name }}
        </h5>
        <button type="button" class="close"
                data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        Are you sure you want to buy {{ item.name }} for {{ item.price }}$ ?
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary"
                data-dismiss="modal">Close
        </button>
      </div>
    </div>
  </div>
</div>
```


![](https://i.imgur.com/WvzeaIU.png)


![](https://i.imgur.com/kN9AZPI.png)


## ⌨️ P15 (5:18:39) Item Purchasing Part 2


![](https://i.imgur.com/BxcddQZ.png)


![](https://i.imgur.com/egr3xOZ.png)


![](https://i.imgur.com/gJ0jGhK.png)


![](https://i.imgur.com/BuZ2Xya.png)


![](https://i.imgur.com/rlHRN5C.png)


![](https://i.imgur.com/GFE5aBv.png)


![](https://i.imgur.com/1F0Fmy4.png)


![](https://i.imgur.com/fqheszq.png)

![](https://i.imgur.com/wxVX2Fe.png)


![](https://i.imgur.com/D4E7UoH.png)


![](https://i.imgur.com/d52U3CP.png)


![](https://i.imgur.com/aYinWBY.png)


![](https://i.imgur.com/PJJa0CQ.png)


![](https://i.imgur.com/VnS8zTE.png)


![](https://i.imgur.com/5ywaTln.png)


![](https://i.imgur.com/Ys5w3mB.png)


![](https://i.imgur.com/lcc5KzM.png)



![](https://i.imgur.com/ZI4MMhG.png)


![](https://i.imgur.com/YCbYHEY.png)




## ⌨️ P16 (5:54:13) Item Selling


![](https://i.imgur.com/77IaCKM.png)


![](https://i.imgur.com/AtWMgAW.png)


![](https://i.imgur.com/EERK42b.png)


![](https://i.imgur.com/H8saiBv.png)


Create new files `owned_items_modals.html`


```
<style>
  .modal-content {
    background-color: #212121
  }
</style>

<div class="modal fade" id="Modal-SellingConfirm-{{ owned_item.id }}"
     tabindex="-1"
     aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="ModalLabel">
          <!-- -->
          {{ owned_item.name }}
        </h5>
        <button type="button" class="close"
                data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <form method="POST">
            {{ selling_form.hidden_tag() }}
          <h4 class="text-center">
             Are you sure you want to sell {{ owned_item.name }} for {{ owned_item.price }}$ ?
          </h4>
          <br>
          <h4 class="text-center">
             Buy clicking Selling, you will put this item back on market.
          </h4>
          <br>
          <input id="sold-item" name="sold-item" type="hidden" value="{{owned_item.name}}">
          {{ selling_form.submit(class="btn btn-outline-danger btn-block") }}
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary"
                data-dismiss="modal">Close
        </button>
      </div>
    </div>
  </div>
</div>
```
![](https://i.imgur.com/A0S2wfF.png)


![](https://i.imgur.com/ARNCNo5.png)


![](https://i.imgur.com/hXURUBl.png)


