---
title: type system
author: teslajuju
date: 2020/03/19
category: type system
---

# 数据类型

## 整数

Python中，整数的表示方法和数学上的写法一模一样，例如 0, 10, -100等。例如，一个值为10的整型变量定义为

    n = 10

## 浮点数

浮点数就是小数。在程序中，一些比较简单的浮点数可以直接写，例如 1.23 0.05 等。对于一些极大或极小的数值，就需要使用科学计数法，例如 12300000，0.00013 可以写成 1.23e7，1.3e-4。

## 字符串

字符串是以单引号或双引号括起来的文本，例如 ‘abc’ 和 “xyz”。

    >>> x = 'tesla'
    >>> print(x)
    tesla

如果字符串中包含少量需要转义的字符，可以使用 **‘\’** 进行转义。例如

    >>> print('\"boy\"')
    "boy"

如果字符串中包含大量需要转义的字符，可以使用 **r'xxx'** 表示不对 xxx 进行转义。例如

    >>> print(r'"boy"')
    "boy"

如果字符串的内容是有大量换行的，可以使用 ''' xxxx ''' 来表示多行内容。例如

    #!/usr/bin/python3
    
    x = '''aaaaaaa
    bbbbbbb
    ccccccc
    ddddddd'''
    
    print(x)

## 布尔值

一个布尔值要么是 True，要么是 False。布尔值可以使用 and or not 进行运算。

## 空值

空值是Python里的一个特殊值，用 None 表示。注意，None 不是0。0是一个有意义的值，None 表示空值。

# 变量

在程序中，变量用一个名字表示。这个名字由大小写英文字母、数字和下划线组成，且开头不能是数字。例如

    n = 12

注意，python的变量有几个特点：

- 同一个变量可以赋予不同类型的值。例如

        >>> x = 3
        >>> print(x)
        3
        >>> x = 'tesla'
        >>> print(x)
        tesla

- 变量是引用语义的，可以理解成C/C++中的指针。例如

        >>> x = 'tesla'
        >>> print(x)
        tesla
        >>>
        >>> y = x
        >>> x = 'yyy'
        >>> print(y)
        tesla

- 习惯用全部大写的变量名表示变量。例如

        PI = 3.1415926