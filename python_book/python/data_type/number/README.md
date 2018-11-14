### Python的Number类型

#### Python支持的数据类型有：整形（int）、浮点型（float）、复数（complex）

* ##### 整形

	* ##### ```int``` 通常被称为整形功整数，是正、负的整数，不带小数点。在```Python 3.x```中没有限制大小，可以当作```long```类型使用，所以```python 3.x```没有```Python 2.x```的```long```类型。

```
num = 51
```

* ##### 浮点

	* ##### ```float```浮点型由整数部分与小数部分组成，也可以使用科学计数法。

```
percent=5.3
```

* ##### 复数

	* ##### ```complex```复数由实数部分跟虚数部分组成，可以用```a+bj```或```complex(a, b)```表示，复数的实数部分```a```和虚数部分```b```都是浮点数，

```
complex(a, b)
```

#### 数据类型转换

	* 整数转换

```
num = "100"
print(int(num)) # int 100

```

	* 浮点型转换

```
num = 100
print(float(num)) # float 103.0
```
	* 复数转换

```
num = 20
age = 103
print(complex(num)) # (20+0j) 将num转换为一个数据，实数是20、虚数是0
print(complex(num, age)) # (20+103j) 将num,age转换为一个复数，num中实数部分，age是虚数部分。num和age是数字表达式。
```