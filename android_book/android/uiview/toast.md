### 提示控件（Toast）

#### Toast控件可以在应用程序中显示一些短小的信息提示给用户，并且这些信息会在过一段时间消失。Toast用法非常简单，通过静态方法```makeText()```创建一个Toast对象，然后调用```show()```方法将Toast显示出来就可以了。

#### 语法：

```Toast.makeText(Context context,Text text,int duration).show()```

#### 参数：

* context	// Toast上下文，由于活动本身就是一个Context对象，因此这里就使用活动本身，传入```MainActivity.this```。
* text		// 要显示的文本信息。
* duration	// Toast显示的时长，有两个内置常量可以选择```Toast.Length_SHORT```和```Toast.LENGTH_LONG```。
