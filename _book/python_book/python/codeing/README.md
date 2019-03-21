# Python中文编码

> 在Python中使用英文字符可以很方便的输入，但是使用中文会编码问题

#### Python 文件中如果未指定编码，在执行过程会出现报错：

```
print('您好世界！')
```

#### 执行会报如下错误：

```
bluelifes-MacBook-Pro:python bluelifeleer$ python file_learn.py 
  File "file_learn.py", line 3
SyntaxError: Non-ASCII character '\xe5' in file file_learn.py on line 3, but no encoding declared; see http://python.org/dev/peps/pep-0263/ for details
```

#### Python中默认的编码格式是 ASCII 格式，在没修改编码格式时无法正确打印汉字，所以在读取中文时会报错。解决方法为只要在文件开头加入 ```#-*- coding: UTF-8-*-``` 或者 ```#coding=utf-8``` 就行了

> 注意：#coding=utf-8 的 = 号两边不要空格。

```
#coding=utf-8
print('您好世界！')
```

##### 最好的方式是在编码时就设置编码方式。

* 注意：Python3.X 源码文件默认使用utf-8编码，所以可以正常解析中文，无需指定 UTF-8 编码。

* 注意：如果使用编辑器，同时需要设置 py 文件存储的格式为 UTF-8，否则会出现类似以下错误信息：

```
SyntaxError: (unicode error) ‘utf-8’ codec can’t decode byte 0xc4 in position 0:
invalid continuation byte
```