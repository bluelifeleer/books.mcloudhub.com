### MapBox setRTLTextPlugin

> 设置地图的RTL文本插件。支持从右到左书写的阿拉伯文和希伯来文等必要的语言。

#### 引入语言插件

```
<script src='https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-language/v0.10.0/mapbox-gl-language.js'></script>
```

#### 设置语言插件

```
mapboxgl.setRTLTextPlugin('https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-rtl-text/v0.1.0/mapbox-gl-rtl-text.js');
```

#### 在实例的地图种设置默认语言
```
map.addControl(new MapboxLanguage({
	defaultLanguage: 'zh'
}));
```

[文档连接：https://www.mapbox.com/mapbox-gl-js/plugins/#mapbox-gl-rtl-text](https://www.mapbox.com/mapbox-gl-js/plugins/#mapbox-gl-rtl-text 'https://www.mapbox.com/mapbox-gl-js/plugins/#mapbox-gl-rtl-text')