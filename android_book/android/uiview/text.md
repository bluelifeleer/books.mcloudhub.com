#### 文本控件（TextView）

```
<TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
```

#### 控件添加```id```

```
android:id="@+id/textView"
```

> ```@```表示非引用

> ```+```表示不存在添加

> ```id```表示要为控件添加id名称

> ```textView```控件的id名称


#### 程序获取控件

* 导入TextView控件

```
import android.widget.TextView;
```

* 定义一个文本控件

```
TextView testView;
```

* 1：通过id获取获取控件，返回名字为id的控件
```
findViewById(R.id.name);
```
* 2：通过文件获取，返回一组控件
```
findViewsWithText();
```
* 3：通过标签获取，返回一个对象
```
findViewByWithTag();
```

#### 设置属性

* 1：设置文本
```
textView.setText();
```
* 2：设置背影颜色
```
textView.setBackgroundColor();
```
* 3：设置文本颜色
```
textView.setTextColor();
```

#### 获取一个颜色(Color)对象

* 1：获取一个RGB的颜色
```
Color.rgb(red,green,blue);
```
* 2：获取一个十六进制的颜色
```
Color.parseColor();
```
* 3：获取一个带透明度的RGB颜色
```
Color.argb(alpha,red,green,blue);
```
* 4：获取一个透明度
```
Color.alpha();
```
* 5：
```
Color.red()
```
* 6：
```
Color.green()
```
* 7：
```
Color.blue()
```

#### 实例

```
package com.example.bluelifeleer.uiview;

import android.graphics.Color;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    private TextView textView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        textView = findViewById(R.id.textView);
        textView = findViewByClass
        textView.setText("text Hello");
        textView.setBackgroundColor(Color.rgb(255,0,0));
        textView.setTextColor(Color.rgb(0,255,0));
    }
}
```