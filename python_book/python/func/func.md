### Python中使用函数

> 函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。
> 函数能提高应用的模块性，和代码的重复利用率。你已经知道Python提供了许多内建函数，比如print()。但你也可以自己创建函数，这被叫做用户自定义函数。



### 函数定义：

* python中使用```def```关銉字定义函数。

```
    def name(parms):
        pass
```


### 实例：

```
    # 定义一个计算总和的函数
    def computedSum(a,b):
        return a+b

    # 调用函数
    sum = computedSum(3,7)
    print("sum:"+ sum) # 10
```

### 函数中参数的类型

* 默认参数：

> 调用函数时，默认参数的值如果没有传入，则被认为是默认值。

```
    def computedSum(a,b=10):
        return a+b
```

* 类键字参数

> 关键字参数和函数调用关系紧密，函数调用使用关键字参数来确定传入的参数值。使用关键字参数允许函数调用时参数的顺序与声明时不一致，因为 Python 解释器能够用参数名匹配参数值。

```
    def printme( str ):
        pass
```

* 不定长参数

> 有时候可能需要一个函数能处理比当初声明时更多的参数。这些参数叫做不定长参数，和上述2种参数不同，声明时不会命名。

```
    def functionname([formal_args,] *var_args_tuple ):
        pass
```

> 加了星号（*）的变量名会存放所有未命名的变量参数。

```
    def printinfo( arg1, *vartuple ):
        "打印任何传入的参数"
        print "输出: "
        print arg1
        for var in vartuple:
            print var
        return;
 
    # 调用printinfo 函数
    printinfo( 10 );
    printinfo( 70, 60, 50 );
```

# 必备参数

> 必备参数须以正确的顺序传入函数。调用时的数量必须和声明时的一样。调用printme()函数，你必须传入一个参数，不然会出现语法错误：

```
#可写函数说明
def printme( str ):
   "打印任何传入的字符串"
   print str;
   return;
 
#调用printme函数
printme();
```