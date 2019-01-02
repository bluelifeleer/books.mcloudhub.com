### ImageView

#### ImageView是一个用于在界面上展示一张图片的控件，图片通常都是放在以```drawable```开头的目录下，由于此目录没有指定图片具体分辨率所以一般不使用它来放置图片。在```res```目录下新建一个```drawable-xhdpi```目录，放置图片。

#### 语法

```
<ImageView>
```

#### 属性：

* android:src	// 指定图片地址
* android:layout_width	// 控件布局宽度
* android:layout_height // 控件布局高度


#### 实例：

```
<ImageView
	android:id="@+id/ImageViewUi"
	android:layout_width="match_parent"
	android:layout_height="wrap_content"
	android:src="@drawable/img_03"/>
```


#### 提示

* 在```Activity```中获取图片：```R.drawable.img_name```。
* 设置图片资源：```ImageViewUi.setImageResouce()```。