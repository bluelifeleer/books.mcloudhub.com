### 复选按纽控件

> 复选按纽控件通常是一组控件中可以同时选中多个按纽控件。

```
<CheckBox
    android:id="@+id/checkboxRed"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_marginTop="10dp"
    android:text="red"/>

<CheckBox
    android:id="@+id/checkboxGreen"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_marginTop="10dp"
    android:text="green"/>

<CheckBox
    android:id="@+id/checkboxBlue"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_marginTop="10dp"
    android:text="blue"/>
```

### 导入包
```
import android.widget.CheckBox;
import android.widget.CompoundButton;
```

### checkbox属性

* setChecked   // 设置控件是否选中
* getId         // 获取控件的ID
* setOnCheckedChangeListener    // 设置复选控件改变事件监听
* setOnClickListener            // 设置复选控件点击事件监听

### 实例

```
// 通过ID获取按纽控件
checkboxRed = findViewById(R.id.checkboxRed);
checkboxGreen = findViewById(R.id.checkboxGreen);
checkboxBlue = findViewById(R.id.checkboxBlue);
// 为按纽控件绑定监听事件
OnCheckBoxChangeListener onCheckboxChangeListener = new OnCheckBoxChangeListener();
checkboxRed.setOnCheckedChangeListener(onCheckboxChangeListener);
checkboxGreen.setOnCheckedChangeListener(onCheckboxChangeListener);
checkboxBlue.setOnCheckedChangeListener(onCheckboxChangeListener);
// 实现一个监听类
class OnCheckBoxChangeListener implements CompoundButton.OnCheckedChangeListener {
    @Override
    public void onCheckedChanged(CompoundButton buttonView, boolean isChecked) {
        if(buttonView.getId() == R.id.checkboxRed){
                System.out.println("red");
        }
        else if(buttonView.getId() == R.id.checkboxGreen){
                System.out.println("Green");
        }else if(buttonView.getId() == R.id.checkboxBlue){
                System.out.println("Blue");
        }
        if(isChecked){
                System.out.println("checked");
        }else{
                System.out.println("UnChecked");
        }
    }
}
```