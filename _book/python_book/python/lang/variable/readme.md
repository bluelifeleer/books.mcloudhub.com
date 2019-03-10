### Python变量

##### 变量定义

> 变量名第一个字符不能使用数字，只能是```a-z,A-Z,_```，除首字符之外可以使用```0-9,a-z,A-Z,_```。

##### 实例：

```
name
_name
name0
name_
office_cup
```
#### 变量赋值

> 变量赋值使用"="符号。

##### 实例

```
num = 123
name = xiaoming
age = 29
```

###### 提示：在未给变量赋值之前变量不可使用。

#### 变量的基本数据类型：

|  数据类型  |  描述  |
|----|----|
|  flot  |  浮点数  |
|  int  |  整型  |
|  long  |  长整型  |
|  str  |  字符串或字符串常量  |

#### 查看变量类型

> 在Python中查看变量类型使用```type```方法

##### 实例

```
cat_name = 'mimi'
type(cat_name)      # <class 'str'>
cat_size = 3
type(cat_size)      # <class 'int'>
```

#### Python获取用户输入

> 在Python中获取用户输入使用```input```方法

##### 实例

```
name = input('输入用户名：')
print('您输入的用户名是：',name)
```

###### 提示：在python2中input是一个表达式所以可以直接使用```input```。

#### Python保留关銉字

'False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield'

#### 查看保留关銉字：

```
import keyword

print(keyword.kwlist)
```