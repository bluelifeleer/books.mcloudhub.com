### 自动将地图语言映射为用户本地化语言

##### mapbox-gl-language是Mapbox Gl Js的一个插件，可以很容易的将它使用在地图中。

#### 使用方法

* 使用CDN


```
<script src='https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-language/v0.10.0/mapbox-gl-language.js'></script>
```

* 使用npm


```
npm install --save mapbox-gl @mapbox/mapbox-gl-language

var mapboxgl = require('mapbox-gl')
var MapboxLanguage = require('@mapbox/mapbox-gl-language');
```


#### MapboxLanguage实例对象

```
new MapboxLanguage(option: object?)
```

* 参数

|  名称  |  描述  |  值类型  |
|----|----|----|
|  options.supportedLanguages  |  设置支持的语言列表  |  Array  |
|  options.languageTransform  |  应用自定义样式转换  |  Function  |
|  options.languageField  |  RegExp匹配如果一个文本字段是一个语言的领域(optional, default /^\{name/)  |  RegExp  |
|  options.getLanguageField  |  给定一种语言，选择向量块中的字段  |  Function  |
|  options.languageSource  |  包含不同语言的源的名称。  |  string  |
|  options.defaultLanguage  |  加载后初始化样式的默认语言的名称。  |  string  |


#### 方法

##### setLanguage 显式更改样式语言

```
MapboxLanguage.setLanguage(style, language)
```


* 参数

	* style 要修改的地图的样式对象
	* language 要修改的系统语言

#### 展示Mapbox街道支持的语言。

	* Your Browser language
	* Arabic
	* Chinese
	* English
	* French
	* German
	* Japanese
	* Korean
	* Multilingual
	* Portuguese
	* Russian
	* Spanish


#### 实例


```
mapboxgl.accessToken = 'YOUR_ACCESS_TOKEN';
var map = new mapboxgl.Map({
    container: 'map',
    style: 'mapbox://styles/mapbox/streets-v10',
    center: [-77.0259, 38.9010],
    zoom: 9
});

// Add RTL support if you want to support Arabic
// mapboxgl.setRTLTextPlugin('https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-rtl-text/v0.1.0/mapbox-gl-rtl-text.js');

var language = new MapboxLanguage();
map.addControl(language);
```



##### [更多详细信息请移步至 https://github.com/mapbox/mapbox-gl-language/](https://github.com/mapbox/mapbox-gl-language/ 'https://github.com/mapbox/mapbox-gl-language/')