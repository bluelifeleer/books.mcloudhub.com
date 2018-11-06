### python循环 

for sept in list:
    pass


### 使用内置函数range()生成一组迭代数字

### 语法

```
range(stop)
range(start,stop[, step])
```

```
list(range(10))
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
list(range(1, 11))
# [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
list(range(0, 30, 5))
# [0, 5, 10, 15, 20, 25]
list(range(0, 10, 3))
# [0, 3, 6, 9]
list(range(0, -10, -1))
# [0, -1, -2, -3, -4, -5, -6, -7, -8, -9]
list(range(0))
# []
list(range(1, 0))
# []
```

### 通过语句

> pass语句什么也不做。当语法上需要语句但程序不需要操作时，可以使用它

```
while True:
    pass  # Busy-wait for keyboard interrupt (Ctrl+C)

```