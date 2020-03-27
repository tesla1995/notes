---
title: type function
author: teslajuju
date: 2020/03/19
category: type system
---

# 类型相关的函数

## 类型转换函数

通过 `int(x)` 函数将数字字符串、浮点数转换、布尔值为整数。例如

```python
>>> int('3')
3
>>> int(3.12)
3
>>> int(True)
1
>>> int(False)
0
>>> int(None)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: int() argument must be a string, a bytes-like object or a number, not 'NoneType'
>>> int('abc')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: 'abc'
```

其他类型转换函数参考[Python内置函数](https://docs.python.org/zh-cn/3/library/functions.html)

## 类型检测

一是通过 `isinstance` 函数判断变量的类型。例如

```python
def my_abs(x):
    if not isinstance(x, (int, float)):
        raise TypeError('bad operand type')
    if x >= 0:
        return x
    else:
        return -x
```
