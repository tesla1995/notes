---
title: function basic
author: teslajuju
date: 2020/03/20
category: function
---

# 函数

## 为什么需要函数

* 封装重复的代码，提高代码的复用性。
* 封装逻辑，提高代码的可读性。

## 定义

以 `def` 关键字开头，依次写出函数名、括号、参数、括号、冒号，然后在缩进块实现逻辑，最后return语句返回函数返回值。例如

```python
def my_abs(x):
    if not isinstance(x, (int, float)):
        raise TypeError('bad operand type')
    if x >= 0:
        return x
    else:
        return -x
```

### 函数参数

* 必选参数：由调用者传入
* 默认参数：调用者不指定变量的值时，使用默认值。减少函数调用难度。
  * 默认参数必须指向不可变对象
  * 如果不按顺序传入默认参数，需要写上参数名
* 可变参数：可以传入任意个参数。
  * 定义时需要在参数前加个 `*` ：`def calc(*numbers):`
  * 调用：`calc(1, 2, 3)`
  * 如果实参 nums 是一个 list 或 tuple，那么 `calc(*nums)`
* 命名关键字参数：限定关键字参数的名字
  * 如果没有可变参数，就必须加一个 `*` 作为特殊分隔符。例如 `def person(name, age, *, city, job):`
  * 如果函数定义中已经有了一个可变参数，后面跟着的命名关键字参数就不再需要一个特殊分隔符 `*` 了。例如 `def person(name, age, *args, city, job):`
  * 命名关键字参数可以有缺省值，从而简化调用。例如 `def person(name, age, *, city='Beijing', job):`
  * 调用时必须指定函数参数名，例如 `person('Jack', 24, city='Beijing', job='Engineer')`
* 关键字参数：允许你传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装为一个dict。用于扩展函数功能。
  * 定义关键字参数的方式为 `def person(name, age, **kw):`
  * 调用 `person('Bob', 35, city='Beijing', job='xxxx')`
  * 调用 `person('Jack', 24, **extra)`，extra是一个 dict。

这五种参数可以互相组合，定义的顺序必须是：必选参数、默认参数、可变参数、命名关键字参数和关键字参数。


### 函数返回值

* 如果函数没有显式的return语句，也会在函数执行完毕后自动 `return None`
* 如果需要返回多个值，需要以逗号分隔。其实，返回的仍然是一个值，只不过这个值是一个tuple。
