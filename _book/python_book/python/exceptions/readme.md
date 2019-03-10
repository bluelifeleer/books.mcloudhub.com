### Python中的异常类（Exceptions）

### 描述

> 在程序运行时或多或少都不可避免的会发生执行错误的时候，在这种情况下可以使用提供的异常类来捕获处理。在Python中，所有异常都必须是派生自BaseException的类的实例。在带有except子句的try语句中，该子句还处理从该类派生的任何异常类(但不处理从其派生的异常类)。两个通过子类化不相关的异常类永远不会是等价的，即使它们有相同的名称。

### 语法

```
try:
	pass # 正常运行的处理
execpt error:
	pass # 发生异常的处理
```

### Python内建异常类

|  名称  |  描述  |
|----|----|
|  Execption  |  常规错误的基类  |
|  AttributeError  |  对象没有这个属性  |
|  IOError  |  输入/输出操作失败  |
|  IndexError  |  序列中没有此索引（index）  |
|  KeyError  |  映射中没有此键  |
|  NameError  |  未声明/初始化对象（没有属性）  |
|  SyntaxError  |  语法错误  |
|  SystemError  |  一般解释器系统错误  |
|  ValueError  |  传入无效参数  |

### 使用

```
```