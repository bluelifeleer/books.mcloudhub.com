### Python的pprint模块

> pprint模块提供了一种“漂亮打印”任意Python数据结构的功能，这种形式可以用作解释器的输入。如果格式化的结构包含非基本Python类型的对象，则表示可能无法加载。如果包含了文件、套接字或类等对象，以及许多其他不能用Python文字表示的对象，则可能出现这种情况。

> 格式化的表示可以将对象保持在一行中，如果它们不符合允许的宽度，则将它们分隔为多行。如果需要调整宽度约束，则显式构造漂亮的打印机对象。

> 在计算显示之前，字典是按键排序的。

### 使用

```
import prrint
```

#### pformat(object, indent=1, width=80, depth=None, \*, compact=False)

> 以字符串的形式返回对象的格式化表示。缩进、宽度、深度和紧凑度将作为格式参数传递给PrettyPrinter构造函数。

* ##### 参数

	* object
	* indent
	* width
	* depth
	* compact

#### pprint.pprint(object, stream=None, indent=1, width=80, depth=None, \*, compact=False)

> 在流中打印格式化的对象表示，后跟换行符。如果流为空，系统。stdout。这可以在交互式解释器中使用，而不是print()函数来检查值(甚至可以重新分配print = pprint)。用于范围内的pprint)。缩进、宽度、深度和紧凑度将作为格式参数传递给PrettyPrinter构造函数。

* ##### 参数

	* object
	* stream
	* indent
	* width
	* depth
	* compact

#### isreadable(object)

> 确定对象的格式化表示是否“可读”，或者可以使用eval()重新构造值。对于递归对象，这总是返回False。

* ##### 参数

	* object

#### isrecursive(object)

> 确定对象是否需要递归表示。

* ##### 参数

	* object

#### saferepr(object)

> 返回对象的字符串表示形式，防止出现递归数据结构。如果对象的表示公开递归条目，递归引用将被表示为id=number>的typename上的<递归。表示没有进行其他格式的格式化。

* ##### 参数

	* object

### 实例

```
#! /usr/bin/python
# -*-coding:UTF-8-*-

import json
import pprint
from urllib.request import urlopen

with urlopen("https://pypi.org/pypi/sampleproject/json") as resp:
    project_info = json.load(resp)[info]
    pprint(project_info)
```

参考连接：

[https://docs.python.org/3/library/pprint.html](https://docs.python.org/3/library/pprint.html 'https://docs.python.org/3/library/pprint.html')