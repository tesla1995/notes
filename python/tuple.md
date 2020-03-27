---
title: tuple
author: teslajuju
date: 2020/03/19
category: data structure
---

# tuple

`tuple` 与 `list` 类似，都是有序集合。但是 `tuple` 一旦初始化，就不可以修改元素的指向。例如

```shell
# 修改tuple的第一个元素的值时抛出了异常

>>> L =('tesla', 13, 2.05, ['gege', 'juju'])
>>> L[0] = 2
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

但是，我们还是能修改元素的内容，例如

```shell
# 我们将list的第一个元素修改为'feifei'

>>> print(L)
['tesla', 13, 2.05, ['gege', 'juju']]
>>> L =('tesla', 13, 2.05, ['gege', 'juju'])
>>> L[3][0] = 'feifei'
>>> print(L)
('tesla', 13, 2.05, ['feifei', 'juju'])
```
