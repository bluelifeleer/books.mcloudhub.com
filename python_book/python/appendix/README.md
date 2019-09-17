### Python中函数及方法信息


#### 数学函数


#### 随机数据函数

#### 三角函数


#### 字符串内奸函数

#### 列表方法

#### 字典内置方法

#### 正则表达式模式

#### python中的```__main__```函数

> '__main__' is the name of the scope in which top-level code executes. A module’s __name__ is set equal to '__main__' when read from standard input, a script, or from an interactive prompt.

> 执行顶级代码的作用域的名称。从标准输入、脚本或交互提示中读取时，模块的“__name__”设置为“__main__”。

> A module can discover whether or not it is running in the main scope by checking its own __name__, which allows a common idiom for conditionally executing code in a module when it is run as a script or with python -m but not when it is imported

> 模块可以通过检查自己的外部名称来发现它是否在作用域中的中运行，这允许使用一种通用的习惯用法，即当模块作为脚本或python-m运行时（而不是在导入时）有条件地在模块中执行代码

> ```__main__```主要作用主要是让该python文件既可以独立运行，也可以当做模块导入到其他文件。当导入到其他的脚本文件的时候，此时__name__的名字其实是导入模块的名字，不是’__main__’, main代码里面的就不执行了。

```
def main():
	print('func main')

if __main__ == 'main':
	main()
```