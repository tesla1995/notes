---
title: basic constrol structure
author: teslajuju
date: 2020/03/19
category: constrol structure
tags: if for
---

# 基础控制结构

基础控制结构包含：条件判断和循环

## 条件判断

条件判断使得计算机能够动态执行不同的任务。例如判断年龄：

```python
age = 3

if age >= 18:
    print('adult')
elif age >= 6:
    print('teenage')
else:
    print('kid')
```

注意：

* 代码行末尾没有分号
* python 用缩进表示代码层级
* 条件判断的末尾都有一个冒号

## 循环

### 基础

循环使得计算机能够做重复的任务。python 中有两种循环，一种是 `for x in ....` 循环；一种是 while 循环。

第一种：`for x in ...` 循环，变量 x 会依次绑定集合中的元素，执行缩进代码块。例如，可以这样遍历一个list,

```python
list = ['tesla', 'qiuy', 'juju']

for x in list:
    print(x)
```

执行这段代码，会依次打印list的元素，

```shell
$ python for_in.py
tesla
qiuy
juju
```

第二种：`while` 循环只要条件为真，就执行缩进代码块。条件为假时退出循环。例如，可以计算 1+2+...+100 之和，

```python
x = 1
result = 0
while x <= 100:
    result += x
    x += 1

print('1+2+...+100 =', result)
```

执行这段代码，会打印

```shell
$ python while.py
1+2+...+100 = 5050
```

另外，循环还有

* `break` 语句，可以直接跳出循环
* `continue` 语句，可以结束当前循环，直接进入下一个循环。

> 建议：代码中少用 break 和 continue，增强代码可读性。

### 迭代

for 循环可用于任何可以迭代的对象。

#### 对象是否可迭代

如何判断一个对象是否可以迭代呢？方法是通过 collections.abc 模块的 Iterable 类型判断：

```python
>>> from collections.abc import Iterable
>>> isinstance('abc', Iterable) # str是否可以迭代
True
>>> isinstance([1,2,3], Iterable) # list是否可以迭代
True
>>>  isinstance(123, Iterable)
  File "<stdin>", line 1
    isinstance(123, Iterable)
    ^
IndentationError: unexpected indent
```

#### 迭代字符串

迭代字符串中的字符，例如

```python
>>> for c in 'abcdef':
...     print(c)
...
a
b
c
d
e
f
```

#### 迭代list或tuple

只迭代 list 的元素，例如

```python
>>> L = ['tesla', 'gege', 'juju']
>>> L
['tesla', 'gege', 'juju']
>>> for value in L:
...     print(value)
...
tesla
gege
juju
```

同时迭代 list 的下标和元素，例如

```python
>>> for i, value in enumerate(L):
...     print(i, ':', value)
...
0 : tesla
1 : gege
2 : juju
```

#### 迭代dict

只迭代key，例如

```python
>>> d
{'a': 1, 'b': 2, 'c': 3}
>>> for key in d:
...     print(key)
...
a
b
c
```

只迭代value，例如

```python
>>> d
{'a': 1, 'b': 2, 'c': 3}
>>> for value in d.values():
...     print(value)
...
1
2
3
```

同时迭代key，value，例如

```python
>>> for k, v in d.items():
...     print(k, '=', v)
...
a = 1
b = 2
c = 3
```
