QuickORM
========

A simple ORM provides elegant API for Python-MySQL operation

Connect to database
-------------------

```python
from data_handler import Database
Database.connect(host='localhost', port=3306, user='root', passwd='123456')
```

Define a model
--------------

```python
class TestModel(Model):
  db_table = 'test'
  a = Field()
  b = Field()
```

Insert
------

```python
test = TestModel()
test.a = 5
test.b = 'john'
test.save()
```

Query
-----

```python
for r in TestModel.where(a=5, b='john').select():
  print r.a
  print r.b
```

Count
-----

```python
print TestModel.where(a=5, b='john').count()
```

Update
------

```python
TestModel.where(a=5, b='john').update(a=1)
```