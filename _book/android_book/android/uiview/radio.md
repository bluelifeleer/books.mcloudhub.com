### 单选控件

> 单靠按纽通常是一组按纽控件中只能有一个被选中。

```
<RadioGroup
    android:id="@+id/radioGroup"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="horizontal">
        <RadioButton
            android:id="@+id/radioNan"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="男"/>
        <RadioButton
            android:id="@+id/radioNv"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="女"/>
</RadioGroup>
```

#### 导入包

```
import android.widget.RadioButton;
import android.widget.RadioGroup;
```

#### 属性

* getId()   // 获取控件的id
* setChecked(boolean true)  // 设置控件是否选中

#### 实例

```
// 定义按纽控件
private RadioGroup radioGroup;
private RadioButton radioNan;
private RadioButton radioNv;
// 获取对应的控件实例
radioGroup = findViewById(R.id.radioGroup);
radioNan = findViewById(R.id.radioNan);
radioNv = findViewById(R.id.radioNv);
// 初始化一个监听事件
RadioOnCheckedChangeListener listener = new RadioOnCheckedChangeListener();
// 将事件绑定在单选控件组上
radioGroup.setOnCheckedChangeListener(listener);
// 实现单选按纽控件改变的监听方法
class RadioOnCheckedChangeListener implements RadioGroup.OnCheckedChangeListener{
    @Override
    public void onCheckedChanged(RadioGroup group, int checkedId) {
        if(radioNan.getId() == checkedId){
            System.out.println("男");
        }
        if(radioNv.getId() == checkedId){
            System.out.println("女");
        }
    }
}
```