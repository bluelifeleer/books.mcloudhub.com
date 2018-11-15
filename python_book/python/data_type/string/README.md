### Python中的字符串

> 像其他语言一样Python也可以操作字符串，在Python中字符串使用单引号(')或者双引号(")定义。在Python字符串中要使用特殊符号可以使用转义符(\)来转义。

#### 实例

```
name = 'bluelife'
print(name) # bluelife
names = "suxiaoxiao"
print(names) # suxiaoxiao
test = '"abcdefg"'
print(test) # "abcdefg"
dir = 'C:\some\name'
print(dir)
# C:\some
# ame
```

##### 提示：如果不想让转义字符生效可以在第一个字符串之前加```r```修饰符说明不转义。

```
dir = r'C:\some\name'
print(dir)
# C:\some\name
```

#### 字符串拼接，在python中字符串拼接使用```+```，可以连接字符串或变量。

```
str1 = 'py'
str2 = 'thon'
fullStr = str1+str2
print(fullStr)
# python
```

#### 在python中如果想输出多个相同的字符可以使用```*```

```
str = 'un'
print(3*str)
# ununun
```

#### 相邻的两个或多个字符串字面值(即引号之间的字符串)会自动连接。

```
'Py' 'thon'
# Python
```

#### 字符串的索引（下标），每个字符是一个字节。

```
str = 'abcdefg'
print(str[2])
# c
```
###### 提示：python中字符串的下标索引开始为0。

#### 也可以使用下标为负数的索引，从右边开始，起始为-1

```
str = 'abcdefg'
print(str[-3])
# e
```
###### 注意，因为-0和0是一样的，负指标从-1开始。

#### 除了索引，也可以使用切片。当索引用于获取单个字符时，切片允许您获取子字符串:

```
word[0:2]  # characters from position 0 (included) to 2 (excluded)
'Py'
>>> word[2:5]  # characters from position 2 (included) to 5 (excluded)
'tho'
```

#### 字符串不支持使用下标去修改

```
word[0] = 'J'
#Traceback (most recent call last):
#  File "<pyshell#4>", line 1, in <module>
#    word[0] = 'J'
#TypeError: 'str' object does not support item assignment
```

#### 如果要通过下标修改字符串，可以重新创建一个新的

```
'J'+word[1:]
'Jython'
```

#### 获取字符串的长度，可以使用len()函数获取。

```
len(word)
# 6
```

### Python中的反义字符串

|  转义字符  |  描述  |
|----|----|
|  \(写在行尾)  |  续行符  |
|  \\  |  反斜杠符号  |
|  \'  |  单引号  |
|  \"  |  双引号  |
|  \a  |  响玲  |
|  \b  |  退格  |
|  \e  |  转义  |
|  \000  |  空  |
|  \n  |  换行  |
|  \v  |  纵向制表符  |
|  \t  |  横向制表符  |
|  \r  |  回车  |
|  \f  |  换页  |
|  \oyy  |  八进制数，yy代表的字符，如：\o12代表换行  |
|  \xyy  |  十六进制数，yy代表的字符，如：\x0a代表换行  |
|  \other  |  其他字符以普通格式输出  |


### Python中的字符串格式化符号

|  符号  |  描述  |
|----|----|
|  %s  |  格式化字符串  |
|  %d  |  格式化整数  |
|  %c  |  格式化字符串及ASCII码  |
|  %u  |  格式化无符号整数  |
|  %o  |  格式化无符号八进制数  |
|  %x  |  格式化无符号十六进制数  |
|  %X  |  格式化无符号十六进制数（大写）  |
|  %f  |  格式化浮点数，可指定精度值  |
|  %e  |  用科学计数法格式化浮点数  |
|  %E  |  作用同%e，用科学计数法格式化浮点数  |
|  %g  |  %f和%e的简写  |
|  %G  |  %f和%E的简写  |
|  %p  |  用十六进制数格式化变量的地址  |

### 实例


* ###### 1:字符串简单格式化


```
>>> print("hello %s" % "word")
>>> hello word

>>> print("num : %d" % 10)
>>> num : 10

>>> print("圆周率PI的值是：%f" %3.1415926)
>>> 圆周率PI的值是：3.141593
```

* ###### 2:字段宽度和精度

	语法：
		
	```
	%宽度.精度
	```

	实例：

	```
	>>> print("圆周率PI的值是：%.3f" % 3.1415926)
	>>> 圆周率PI的值是：3.142
	>>> print("圆周率PI的值是：%10.3f" % 3.1415926)
	>>> 圆周率PI的值是：     3.142
	>>> print("字符串精度：%.5s" % "hello word")
	>>> 字符串精度：hello
	>>> print("从元组中获取字符串精度：%*.*s" % (10,5, "hell oword"))
	>>> 从元组中获取字符串精度：     hell 
	>>> print("从元组中获取字符串精度：%.*s" % (5, "hell oword"))
	>>> 从元组中获取字符串精度：hell 
	```

* ###### 3:符号、对齐和0填充
	语法：

	```
	%填充宽度.精度
	```

	实例：

	```
	>>> print("钢笔单价：%.2f" %3.5)
	>>> 钢笔单价：3.50
	>>> print("钢笔单价：%05.2f" %3.5)
	>>> 钢笔单价：03.50
	>>> print("字符串 %-10.3s" % "aaaa")
	```

###### 填充可以使用-,+,0或空格，0表示用0填充。

### 字符串的操作方法：

|  名称  |  描述  |  语法及参数  |
|----|----|
|  find()  |  检测字符串中是否包含子字符串  |  str.find(start,begin=0,end=len(str))  |
|  join()  |  将序列中的元素以指定字符连接成一个新字符串  |  str.join(sequence)  |
|  lower()  |  将字符串中所有大写转成小写  |  str.lower()  |
|  upper()  |  将字符串中所有小写转成大写  |  str.upper()  |
|  swapcase()  |  对字符串中的大小写进行转换，大写转成小写，小写转成大写  |  str.swapcase()  |
|  replace()  |  把字符串中旧的字符串用新的字符串替换  |  str.replace(old,new[,max]) ,max指定替换的次数 |
|  split()  |  通过指定分隔符对字符串进行切片  |  str.split(str='',num=string.count(str))  |
|  strip()  |  用于移除字符串头尾指定的字符（默认是空格）  |  str.strip([chars])  |
|  translate()  |  根据参数table给出的表（包含256个字符），转换字符串的字符，将要过滤掉的字符放到del参数中去  |  str.translate(table[,deletechars])  |


#### 实例：

