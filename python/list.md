---
title: list
author: teslajuju
date: 2020/03/19
category: data structure
---

# list

## list是什么

`list` 是一种有序集合，可以添加和删除元素。

## 适用场景

根据list的特点，其适用场景为：

* 业务上：适用于顺序存储数据的场景
* 技术上：适用于根据下标随机访问的场景

## 操作

### 新增

`append`：在末尾追加一个元素。例如

```shell
>>> L = ['tesla','qiuy']
>>> print(L)
['tesla', 'qiuy']
>>> L.append('gege')
>>> print(L)
['tesla', 'qiuy', 'gege']
```

`insert`：在指定位置插入元素。例如

```shell
>>> print(L)
['tesla', 'qiuy', 'gege']
>>> L.insert(0, '2222')
>>> print(L)
['2222', 'tesla', 'qiuy', 'gege']
```

### 删除

`pop`：删除末尾的元素。例如

```shell
>>> print(L)
['2222', 'tesla', 'qiuy', 'gege']
>>> L.pop()
'gege'
>>> print(L)
['2222', 'tesla', 'qiuy']
```

`pop(i)`：删除指定位置的元素。例如

```shell
>>> print(L)
['2222', 'tesla', 'qiuy']
>>> L.pop(0)
'2222'
>>> print(L)
['tesla', 'qiuy']
```

### 查询

使用下标运算符 `[]` 访问指定位置的元素。

```shell
>>> print(L)
['tesla', 'qiuy']
>>> print(L[0])
tesla
>>> print(L[1])
qiuy
```

### 修改

使用下标运算符 `[]` 修改指定位置的元素。

```shell
>>> print(L)
['tesla', 'qiuy']
>>> L[0] = 'teslajuju'
>>> print(L)
['teslajuju', 'qiuy']
```

### 元素类型不必相同

`list` 中元素类型可以是不同的数据类型，甚至可以是一个list，例如

```shell
>>> L = ['tesla', 13, 2.05, ['gege', 'juju']]
>>> print(L)
['tesla', 13, 2.05, ['gege', 'juju']]
```
