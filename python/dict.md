---
title: dict
author: teslajuju
date: 2020/03/20
category: data structure
---

# dict

## 定义

`dict` 存储了键值对，适用于**快速查找**。

## 操作

### 初始化

创建一个空的 `dict`，

```python
>>> d = {}
>>> print(d)
{}
```

以大括号包裹，以逗号分隔的键值对来创建一个 `dict`，

```python
>>> d = {'tesla':25, 'juju':18, 'qiuy':22}
>>> print(d)
{'tesla': 25, 'juju': 18, 'qiuy': 22}
```

### 添加或者更新

使用下标运算符 `[]` 可以增加或更新键值对。多次更新同一个键的值，后面的值会冲掉前面的值。

```python
>>> print(d)
{'tesla': 99, 'juju': 18, 'qiuy': 22}
>>> d['kkk'] = 88
>>> print(d)
{'tesla': 99, 'juju': 18, 'qiuy': 22, 'kkk': 88}
>>> d['kkk'] = 30
>>> print(d)
{'tesla': 99, 'juju': 18, 'qiuy': 22, 'kkk': 30}
```

### 访问

一是使用下标运算符 `[]` 可以访问键对应的值。如果键不存在会报错。

```python
>>> d['kkk']
30
>>> d['jjj']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'jjj'
```

二是使用 `dict` 提供的 `get()` 方法，如果 key 不存在，返回一个 `None` 或者自己指定的值。

```python
>>> d.get('jjj') # None 在界面上不显示
>>> d.get('jjj', -1)
-1
```

### 删除

使用 `pop(key)` 方法删除一个指定的键值对，

```python
>>> print(d)
{'tesla': 99, 'juju': 18, 'qiuy': 22, 'kkk': 30}
>>> d.pop('kkk')
30
>>> print(d)
{'tesla': 99, 'juju': 18, 'qiuy': 22}
```
