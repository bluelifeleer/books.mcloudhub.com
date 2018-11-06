### Android中的日志工具(Log)

#### Log方法：

> Android中的日志工具类Log（android.util.Log）,这个类提供了5个方法来供我们打印日志。

* Log.v()用于打印那些最为琐碎、意义最小的日志。对应级别verbose，是Android日志里面级别最低的一种。

* Log.d()用于打印一些调试信息，这些信息对程序调试分析问题是有帮助的，对应级别debbug，比verbos高一些。

* Log.i()用于打印一些比较重要的数据，这些数据是埋深想看到的可能帮助分析用户行为数据，对应级别info，比debug高级一些。

* Log.w()用于打印一些警告信息，提示程序在这个地方会有潜在风险，最好修复一下这些出现警告的地方，对应级别warn，比info高级一些。

* Log.e()用于打印程序中出现的错误信息，比如程序进入到了catch语句中。当有错误信息打印出来的时候。一般都代表程序出现的严重的问题，对应级别error，比warn高级一些。

#### 引入的类：Android.util.Log

```
import android.util.Log;
```

#### 实例：

```
Log.d("MainActivity","onCreate execcute");
```

#### 参数：

###### ```Log.d()```传入两个参数：第一个参数是```tag```，一般传入当前的类名，主要用于对打印的信息进入过滤；第二个参数是```msg```，是想要打印的信息内容。


#### 提示：

##### 在Android Studio中快速输入要使用的日志：比如要Log.d()，快捷銉：```logd```按Tab銉即可。
##### 在onCcreate()方法外输入logt按Tab銉，wfcc生成一个以当前类名为值自动生成一个TAG常量如下所示：

```
public class MainActivity extends AppCompatActivity {

		// 自动生成一个以当前类名为值的TAG常量
    private static final String TAG = "MainActivity";
    
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Log.d("MainActivity","onCreate execute");
    }
}
```