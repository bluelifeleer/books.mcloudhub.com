# Python序列化与反序列化

### 一般数据的序列化

> Python的```pickle```模块实现了基本数据的序列化和反序列化，通过```pickle```模块的序列化操作，能够将程序中运行的对象信息保存到文件中，从而永久存储，通过```pickle```模块的反序列化操作，能够从文件中创建上一次保存的程序。


#### 语法：

##### pickle.dump(obj, file, protocol=None, * , fix_imports=True)

> 将obj的pickled表示形式写入打开的文件对象文件。这相当于pickler（文件，协议）.dump（obj）。

> 可选的协议参数是一个整数，它告诉pickler使用给定的协议；支持的协议是0到最高的协议。如果未指定，则默认为默认协议。如果指定负数，则选择最高的协议。

> 文件参数必须有一个接受单字节参数的write（）方法。因此，它可以是一个为二进制写入而打开的磁盘上文件、一个IO.Bytesio实例或满足此接口的任何其他自定义对象。

>如果fix_导入为真且协议小于3，pickle将尝试将新的python 3名称映射到python 2中使用的旧模块名称，以便pickle数据流可以用python 2读取。

##### pickle.dumps(obj, protocol=None, * , fix_imports=True)

> 以字节对象的形式返回对象序列化后的结果，而不是写入文件。

##### pickle.load(file, * , fix_imports=True, encoding="ASCII", errors="strict")

> 从打开的文件对象文件中读取pickled对象表示，并返回其中指定的重新构建的对象层次结构。这相当于unpickler（file.load（）。

>自动检测pickle的协议版本，因此不需要协议参数。超过pickled对象表示形式的字节将被忽略。

> 参数文件必须有两个方法，一个采用整数参数的read（）方法和一个不需要参数的readline（）方法。两种方法都应返回字节。因此，文件可以是为二进制读取而打开的磁盘上文件、IO.Bytesio对象或满足此接口的任何其他自定义对象。

> 可选关键字参数包括fix_导入、编码和错误，这些参数用于控制由python 2生成的pickle流的兼容性支持。如果fix_imports为true，pickle将尝试将旧的python 2名称映射到python 3中使用的新名称。编码和错误告诉pickle如何解码由python 2处理的8位字符串实例；它们分别默认为“ascii”和“strict”。编码可以是“字节”，以将这些8位字符串实例读取为字节对象。需要使用encoding='latin1'来取消拾取由python 2处理的numpy数组和date time、日期和时间实例。

##### pickle.loads(bytes_object, * , fix_imports=True, encoding="ASCII", errors="strict")

> 从bytes对象读取pickled对象层次结构，并返回其中指定的重新构建的对象层次结构。

> 自动检测pickle的协议版本，因此不需要协议参数。超过pickled对象表示形式的字节将被忽略。

> 可选关键字参数包括fix_导入、编码和错误，这些参数用于控制由python 2生成的pickle流的兼容性支持。如果fix_imports为true，pickle将尝试将旧的python 2名称映射到python 3中使用的新名称。编码和错误告诉pickle如何解码由python 2处理的8位字符串实例；它们分别默认为“ascii”和“strict”。编码可以是“字节”，以将这些8位字符串实例读取为字节对象。需要使用encoding='latin1'来取消拾取由python 2处理的numpy数组和date time、日期和时间实例。

### JSON数据的序列化

> JSON（JavaScript Object Notation[javascript对象表示法]），由RFC 7159（废弃RFC 4627）和ECMA-404指定，是一种受javascript对象文本语法启发的轻量级数据交换格式（尽管它不是javascript[1]的严格子集）。

#### 语法：

##### JSON.dumps()

##### 实例：

```
>>> import json
>>> json.dumps(['foo', {'bar': ('baz', None, 1.0, 2)}])
'["foo", {"bar": ["baz", null, 1.0, 2]}]'
>>> print(json.dumps("\"foo\bar"))
"\"foo\bar"
>>> print(json.dumps('\u1234'))
"\u1234"
>>> print(json.dumps('\\'))
"\\"
>>> print(json.dumps({"c": 0, "b": 0, "a": 0}, sort_keys=True))
{"a": 0, "b": 0, "c": 0}
>>> from io import StringIO
>>> io = StringIO()
>>> json.dump(['streaming API'], io)
>>> io.getvalue()
'["streaming API"]'
```

> 对数数据进行编码

##### JSON.loads()

##### 实例

```
>>> import json
>>> json.loads('["foo", {"bar":["baz", null, 1.0, 2]}]')
['foo', {'bar': ['baz', None, 1.0, 2]}]
>>> json.loads('"\\"foo\\bar"')
'"foo\x08ar'
>>> from io import StringIO
>>> io = StringIO('["streaming API"]')
>>> json.load(io)
['streaming API']
```

> 对数据进行解码


###### pickle协议和json（javascript对象表示法）之间存在根本区别：


* JSON是一种文本序列化格式（它输出Unicode文本，尽管大多数时候它被编码为UTF-8），而pickle是一种二进制序列化格式；

* JSON是人类可读的，而pickle则不是；

* JSON是可互操作的，在Python生态系统之外被广泛使用，而pickle是特定于Python的；

* 默认情况下，JSON只能表示Python内置类型的一个子集，不能表示自定义类；pickle可以表示非常多的Python类型（其中许多类型是通过巧妙地使用Python的内省功能自动生成的；通过实现特定的对象API可以处理复杂的情况）。

###### 在JSON编码解码过程中，python的原始类型与JSON类型会相互转换，具体的转换对照如下:

* Python转换JSON

|  Python  |  JSON  |
|----|----|
|  dict  |  object  |
|  list,tuple  |  array  |
|  str  |  string  |
|  int,float,int- & float-derived Enums  |  number  |
|  True  |  true  |
|  False  |  false  |
|  None  |  null  |

* JSON转换Python

|  JSON  |  Python  |
|----|----|
|  object  |  dict  |
|  array  |  list  |
|  string  |  str  |
|  number(int)  |  int  |
|  number(real)  |  float  |
|  true  |  True  |
|  false  |  Flase  |
|  null  |  None  |

###### 文档连接：

* [https://docs.python.org/3/library/pickle.html](https://docs.python.org/3/library/pickle.html 'https://docs.python.org/3/library/pickle.html')

* [https://docs.python.org/3/library/json.html#module-json](https://docs.python.org/3/library/json.html#module-json 'https://docs.python.org/3/library/json.html#module-json')