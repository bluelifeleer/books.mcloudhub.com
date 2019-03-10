### Python各个版本区别

#### python 2.x跟python 3.x之间的主要区别

* 1）使用__future__模块

	##### Python 3.x引入了一些与Python 2.x不兼容的关键字和特性。在python 2.x中可以通过内置的__future__模块导入这些新内容。如果希望在python 2.x中代码也可以在python 3.x中运行，那么建议使用__future__模块。

* 2）print()函数

	##### 在python 2.x中print是一个语句，这意味着使用print可以不需要括号，但是在python 3.x中print是一个函数，必需要加括号。

	```
	# python 2.x
	print "Hello word"
	# python 3.x
	print("Hello word")
	```
	###### 如果在python 3.x中使用print不加括号将触发SyntaxError(语法错误)

* 3）异常处理

	#### python 3.x中处理异常必需使用```as```关键字，在python 2.x中不需要。

* 4）使用input()解析输入内容

	#### 在Python 3.x中改进了print()函数，该函数会总是将用户输入```input()```存储为str对象。在python 2.x中为了避免读取非字符串类型会发生一些危险的行为，不得不使用```raw_input()```代替```input()```。

* 5）返回可迭代对象而不是列表

	#### 某些函数和方法在python 3.x中返回的是可迭代的对象，而不像在python 2.x中返回列表。对象遍历一次会节省很多内存，如果通过生成器多次迭代这些对象，效率就不高了。此时如果需要列表对象，可以使用python 3.x的```list()```函数简单的将迭代对象转换成列表。
