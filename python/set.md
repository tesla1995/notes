---
title: set
author: teslajuju
date: 2020/03/19
category: data structure
---

# set

## 定义

set 是一个无序、不重复的集合。与 dict 相比，只存储了键，没有存储值。而且，这个键应该是一个**不可修改**的对象，例如 list 就不能作为键使用。

## 操作

### 初始化

初始化一个空的 set。

```python
s = set()
```

从 list 初始化一个 set 出来。

```python
s = set([1, 2, 3])
```

### 添加key

通过 `add(key)` 添加key，例如

```shell
>>> s = set([1, 2, 3])
>>> print(s)
{1, 2, 3}
>>> s.add(4)
>>> print(s)
{1, 2, 3, 4}
```

### 删除key

通过 `remove(key)` 删除key，例如

```shell
>>> print(s)
{1, 2, 3, 4}
>>> s.remove(2)
>>> print(s)
{1, 3, 4}
```

## 使用场景

求两个集合的交集、并集、差集。

```python
>>> s1 = set([1, 2, 3])
>>> print(s1)
{1, 2, 3}
>>> s2 = set([3, 4, 5])
>>> print(s2)
{3, 4, 5}
>>> s1 | s2  # 求并集，即两个集合的所有元素
{1, 2, 3, 4, 5}
>>> s1 & s2  # 求交集，即两个集合中都有的元素
{3}
>>> s1 - s2  # 求差集，即在s1中，但不在s2中的元素
{1, 2}
```
