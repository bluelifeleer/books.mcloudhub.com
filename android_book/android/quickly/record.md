### 获取应用名称

* 在java中
	```
		R.string.app_name
	```
* 在XML中

	```
	@string/app_name
	```

### setContentView()方法来给当前活动加载一个布局。

### Mac下Android Studio中获取SHA1和MD5以及SHA256证书指纹
```
	keytool -list -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass android
```