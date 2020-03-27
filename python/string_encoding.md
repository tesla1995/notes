# 字符编码

不同字符编码：

- ASCII编码用1个字节表示1个字符，只支持英文。
- Unicode编码使用2个字节表示1个字符，特别偏僻的字符需要4个字节，支持多语言。但是，存储英文时，比ASCII编码多了一倍的存储空间，不利于存储和传输。
- UTF-8编码使用1个字节编码英文字符，3个字节编码中文字符，特别偏僻的字符需要4~6个字节。支持多语言。常用于存储和传输。

现代计算机使用编码的方式为：在计算机内存中使用Unicode编码，存储和传输使用UTF-8编码。

# Python的字符串

python3中的字符串使用Unicode编码，也就是支持多语言。如果要保存到磁盘，或者通过网络传输，就必须转换为utf-8。反之亦然。例如

    #!/usr/bin/env python3
    # -*- coding: utf-8 -*-
    
    text = '中文'
    encode = text.encode('utf-8');
    new_text = encode.decode('utf-8')
    print(new_text)

# 格式化

Python使用 % 运算符表示要对字符串进行格式化。字符串内部使用占位符表示要用哪种类型的数据替换，

| 占位符 | 替换内容   |
| ------ | ---------- |
| %d     | 整数       |
| %f     | 浮点数     |
| %s     | 字符串     |
| %x     | 十六进制数 |

例如，

    #!/usr/bin/env python3
    # -*- coding: utf-8 -*-
    
    name = 'tesla'
    age = 25
    print('The age of %s is %d' % (name, age))