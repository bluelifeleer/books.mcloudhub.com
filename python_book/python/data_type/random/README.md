# python随机数

### 导入模块

```
import random
```

### 随机整数

```
print(random.randint(0,100))
```

### 随机选取0到100间的偶数

```
random.randrange(0, 101, 2)
```

### 随机浮点数

```
print(random.random())
```

### 随机字符串

```
random.choice('abcdefg&#%^*f')
```

### 随机长度的字符串

```
random.sample('abcdefghij',3)
```

### 随机长度字符串组成新字符串

```
import string
string.join(random.sample('abcdefghij',3)).replace(" ","")
```

### 从列表中选取随机字符串

```
list=['apple', 'pear', 'peach', 'orange', 'lemon']
random.choice(list)
```

### 重新排序

```
items = [1, 2, 3, 4, 5, 6]
random.shuffle(items)
print(items)
```

[文档连接：https://docs.python.org/3.7/library/random](https://docs.python.org/3.7/library/random 'https://docs.python.org/3.7/library/random')