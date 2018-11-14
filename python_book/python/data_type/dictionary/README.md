### Python中的字典

#### 描述

> Python 内建的另一个有用的数据类型是字典(请参阅映射类型- dict)。在其他语言中，字典有时被称为“联想记忆”或“联想数组”。与用一系列数字索引的序列不同，字典是用键索引的，键可以是任何不可变的类型;字符串和数字总是键。如果元组只包含字符串、数字或元组，则可以将其用作键;如果一个元组直接或间接包含任何可变对象，它就不能用作键。不能将列表用作键，因为可以使用索引赋值、切片赋值或 append()和 extend()之类的方法在适当的位置修改列表。 最好将字典看作一组无序的键:值对，要求键是唯一的(在一个字典中)。一对大括号创建一个空字典:{}。在大括号中放置逗号分隔的键:值对将初始键:值对添加到字典中;这也是在输出中编写字典的方式。 字典上的主要操作是用某个键存储值并提取给定键的值。也可以删除带有 del 的键:值对。如果您使用已经在使用的键存储，那么与该键关联的旧值将被遗忘。使用不存在的键提取值是错误的。 在字典上执行 list(d.keys())将返回字典中使用的所有键的列表，顺序是任意的(如果您想排序，只需使用已排序的(d.keys()))。若要检查字典中是否有单个键，请使用 in 关键字。[[来自 https://docs.python.org/3.5/tutorial/datastructures.html?highlight=dictionary](https://docs.python.org/3.5/tutorial/datastructures.html?highlight=dictionary 'https://docs.python.org/3.5/tutorial/datastructures.html?highlight=dictionary')]


#### 字典定义

###### 定义一个保存人的信息的字典。
```
people = {"name":"xiaoxiaosu","sex":1,"age":25,"work":""}
```
#### 读取字典中的值。
###### 在字典中通过 key 可以获取对应的值，如：

```
print('The people`s name %s .' $(people['name])) # The people`s name xiaoxiaosu .
```

#### 内置方法
|  方法  |	描述  |  参数  |
|----|----|----|
|  dic.clear()  |	删除字典内所有元素  |	none |
|  dic.copy()  |	对一个字典的浅拷贝  |	none |
|  dic.formkeys(sqp,val)  |	创建一个新字典，以序列 seq 中元素做字典的键，val 为字典所有键对应的初始值  |	sqp,val |
|  dic.get(key,default=None)  |	返回指定键的值，如果值不在字典中返回 default 值  |	key |
|  dic.has_key()  |	判断字典中某个键是否存在  |	key |
|  dic.item()  |	以列表返回可遍历的(键, 值) 元组数组  |	none |
|  dic.keys()  |	以列表返回一个字典所有的键  |	none |
|  dic.setDefault(key, default=None)  |	和 get()类似, 但如果键不存在于字典中，将会添加键并将值设为 default  |	key |
|  dic.update(dic1)  |	把 dic1 中的键值更新到 dic 中  |	dic1 |
|  dic.values()  |	以列表形式返回字典中所有的值  |	none |
|  dic.pop(key[,dfault])  |	删除字典给定键 key 所对应的值，返回值为被删除的值。key 值必须给出。 否则，返回 default 值。  |	key |
|  dic.popitem()  |	随机返回并删除字典中的一对键和值。  |	none |

#### 内置函数
|  函数 | 描述 | 参数 |
|----|----|----|
|  cmp(dic1,dic2)  |  比较两个字典的元素  |  dic1,dic2  |
|  len(dic)  | 计算字典的长度 | dic |
|  str() | 将字典以字符串的形式打印 | dic |
|  type() | 返回输入的变量的类型，如果是字典就输出字典类型 | dic |

###### 提示：在 python3.x 中判断字典中是否存在一个键使用__contains__来判断。
```
dic.has_key(key)   # python2.x
dic.__contains__(key) # python3.x
```

contains 英 [kən'teinz] 美 v. 包含；容纳；包含某字符串（contain 的单三形式） n. 包含
[参考连接：https://docs.python.org/3.5/tutorial/datastructures.html?highlight=dictionary](https://docs.python.org/3.5/tutorial/datastructures.html?highlight=dictionary 'https://docs.python.org/3.5/tutorial/datastructures.html?highlight=dictionary')