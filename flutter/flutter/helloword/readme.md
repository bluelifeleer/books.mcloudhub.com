# flutter编写```Hello Word```

# 1：创建main.dart文件

```
package:flutter/material.dart

void main() => runApp(new MyApp());

class MyApp extends StatelessWidget{
	@override
	Widget build(BuiltContext context){
		return MaterialApp(
	      title: 'Flutter Demo',
	      debugShowCheckedModeBanner: false,
	      theme: ThemeData(
	        canvasColor: Colors.white,
	        // fontFamily: 'Oxygen',
	        // This is the theme of your application.
	        //
	        // Try running your application with "flutter run". You'll see the
	        // application has a blue toolbar. Then, without quitting the app, try
	        // changing the primarySwatch below to Colors.green and then invoke
	        // "hot reload" (press "r" in the console where you ran "flutter run",
	        // or simply save your changes to "hot reload" in a Flutter IDE).
	        // Notice that the counter didn't reset back to zero; the application
	        // is not restarted.
	        primarySwatch: Colors.blue,
	      ),
	      home: Landing(),
	    );
	}
}
```