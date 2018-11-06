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

##### 提示：如果不想让转义字符生效可以在第一个字符串之前加```r``修饰符说明不转义。

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