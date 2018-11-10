### mapboxgl.Map 中 option 介绍

#### 在初始化 mapboxgl.Map 对象实例时可以指定许多配置的参数，通过 option 来指定：

```
var option = {
  container: '',
  style: '',
  center: [],
  zoom: Number
}
var MapBox = mapboxgl.Map(option);
// or 
var MapBox = mapboxgl.Map({
  container: '',
  style: '',
  center: [],
  zoom: Number
});

```

#### 参数

```
options(Object)
```

|  名称  |  描述  |  值  |
|----|----|----|
|  options.container([HTMLElement](https://developer.mozilla.org/docs/Web/HTML/Element 'https://developer.mozilla.org/docs/Web/HTML/Element') or [string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String'))  |  加载地图的HTML容器id  |  HTMLElement or string  |
|  options.minZoom [number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number')(default 0)  |  地图的最小缩放值  |  Number  |
|  options.maxZoom [number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number')(default 22)  |  地图的最大缩放值  |  Number  |
|  options.style([Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object') or [string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String'))  |  地图的Mapbox样式。这必须是一个符合Mapbox样式规范中描述的模式的JSON对象，或者是此类JSON的URL。要从Mapbox API加载样式，可以使用Mapbox://styles/:owner/:style表单的URL，其中:owner是您的Mapbox帐户名，:style是样式ID。  使用Mapbox托管的Tilesets可以对样式进行优化，如果你在样式URL的末尾添加? optimization =true，比如Mapbox://styles/ Mapbox /street -v9? optimization =true。在[API文档](https://www.mapbox.com/api-documentation/#retrieve-tiles 'https://www.mapbox.com/api-documentation/#retrieve-tiles')中了解更多关于样式优化的向量tiles的信息。  |  mapbox://styles/mapbox/streets-v10 mapbox://styles/mapbox/streets-v10 mapbox://styles/mapbox/outdoors-v10 mapbox://styles/mapbox/light-v9 mapbox://styles/mapbox/dark-v9 mapbox://styles/mapbox/satellite-v9 mapbox://styles/mapbox/satellite-streets-v10 mapbox://styles/mapbox/navigation-preview-day-v2 mapbox://styles/mapbox/navigation-preview-night-v2 mapbox://styles/mapbox/navigation-guidance-day-v2 mapbox://styles/mapbox/navigation-guidance-night-v2  |
|  options.hash [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default false)  |  如果为真，地图的位置(缩放、中心纬度、中心经度、方位和间距)将与页面URL的散列片段同步。例如，http://path/to/my/page.html#2.59/39.26/53.07/-24.1/60。  |  boolean  |
|  options.interactive [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为false，则不会将鼠标、触摸或键盘侦听器附加到映射，因此它不会响应交互。  |  boolean  |
|  options.bearingSnap [number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number')(default 7)  |  这个以度数衡量的门槛，决定了地图的方位何时会向北移动。例如，在bearingSnap为7的情况下，如果用户将地图旋转到北纬7度范围内，地图就会自动地向北移动。  |  number  |
|  options.pitchWithRotate [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为false，将禁用带有“拖动到旋转”交互的地图俯仰控制。  |  boolean  |
|  options.clickTolerance [number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number')(default 3)  |  用户在单击时可以移动鼠标指针的最大像素数，使其被认为是有效的单击(而不是鼠标拖动)。  |  number  |
|  options.attributionControl [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为真，将向映射添加一个AttributionControl。  |  boolean  |
|  options.customAttribution([string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String') or [Array](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array')<[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String')>)?  |  在[AttributionControl](https://www.mapbox.com/mapbox-gl-js/api#attributioncontrol 'https://www.mapbox.com/mapbox-gl-js/api#attributioncontrol')中显示的字符串或字符串。仅适用于if选项。属性控制是真的。  |  string  |
|  options.logoPosition [string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String')(default 'bottom-left')  |  表示Mapbox wordmark在地图上位置的字符串。有效的选项有左上(top-left)、右上(top-right)、左下(bottom-left)、右下(bottom-right)。  |  string  |
|  options.failIfMajorPerformanceCaveat [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default false)  |  如果为真，如果Mapbox GL JS的性能比预期的差很多(也就是说会使用软件渲染器)，那么地图创建就会失败。  |  boolean  |
|  options.preserveDrawingBuffer [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default false)  |  如果为真，Map的canvas将可以被导出为一个PNG图片，可以使用map.getCanvas().toDataURL()，对于性能优化来说这是不推荐的。  |  boolean  |
|  options.refreshExpiredTiles [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为false，在每个HTTP cacheControl / expires头过期后，映射不会尝试重新请求tile。  |  boolean  |
|  options.maxBounds [LngLatBoundsLike](https://www.mapbox.com/mapbox-gl-js/api#lnglatboundslike 'https://www.mapbox.com/mapbox-gl-js/api#lnglatboundslike')?  |  如果设置，映射将被限制到给定的边界。  |  LngLatBoundsLike  |
|  options.scrollZoom(boolean or Object)(default true)  |  如果为真，则启用“滚动缩放”交互。对象值作为选项传递给[ScrollZoomHandler#enable](https://www.mapbox.com/mapbox-gl-js/api#scrollzoomhandlerenable 'https://www.mapbox.com/mapbox-gl-js/api#scrollzoomhandlerenable')。  |  boolean or Object  |
|  options.boxZoom [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为真，则启用“框缩放”交互(请参阅[BoxZoomHandler](https://www.mapbox.com/mapbox-gl-js/api#boxzoomhandler 'https://www.mapbox.com/mapbox-gl-js/api#boxzoomhandler'))。  |  boolean  |
|  options.dragRotate [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为真，则启用“拖动到旋转”交互(参见[DragRotateHandler](https://www.mapbox.com/mapbox-gl-js/api#dragrotatehandler 'https://www.mapbox.com/mapbox-gl-js/api#dragrotatehandler'))。  |  boolean  |
|  options.dragPan [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为真，则启用“拖到pan”交互(请参阅[DragPanHandler](https://www.mapbox.com/mapbox-gl-js/api#dragpanhandler 'https://www.mapbox.com/mapbox-gl-js/api#dragpanhandler'))。  |  boolean  |
|  options.keyboard [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为真，则启用键盘快捷键(参见[KeyboardHandler](https://www.mapbox.com/mapbox-gl-js/api#keyboardhandler 'https://www.mapbox.com/mapbox-gl-js/api#keyboardhandler'))。  |  boolean  |
|  options.doubleClickZoom [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为真，则启用“双击缩放”交互(参见[DoubleClickZoomHandler](https://www.mapbox.com/mapbox-gl-js/api#doubleclickzoomhandler 'https://www.mapbox.com/mapbox-gl-js/api#doubleclickzoomhandler'))。  |  boolean  |
|  options.touchZoomRotate(boolean or Object)(default true)  |  如果为真，则启用“缩放以旋转和缩放”交互。对象值作为选项传递给[TouchZoomRotateHandler#enable](https://www.mapbox.com/mapbox-gl-js/api#touchzoomrotatehandlerenable 'https://www.mapbox.com/mapbox-gl-js/api#touchzoomrotatehandlerenable')。  |  boolean  |
|  options.trackResize [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为真，当浏览器窗口调整大小时，映射将自动调整大小。  |  boolean  |
|  options.center [LngLatLike](https://www.mapbox.com/mapbox-gl-js/api#lnglatlike 'https://www.mapbox.com/mapbox-gl-js/api#lnglatlike')(default [0,0])  |  地图上最原始的地理中心。如果在构造函数选项中没有指定center, Mapbox GL JS将在map的style对象中查找它。如果样式中没有指定它，它将默认为[0,0]注意:Mapbox GL使用经度、纬度坐标顺序(与纬度、经度相反)来匹配GeoJSON。  |  LngLatLike  |
|  options.zoom [number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number')(default 0)  |  地图的初始缩放级别。如果在构造函数选项中没有指定缩放，Mapbox GL JS将在map的style对象中查找它。如果样式中没有指定它，它也将默认为0。  |  number  |
|  options.bearing [number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number')(default 0)  |  地图的初始方位(旋转)，从北向以逆时针的角度测量。如果在构造函数选项中没有指定轴承，Mapbox GL JS将在map的style对象中查找它。如果样式中没有指定它，它也将默认为0。  |  number  |
|  options.pitch [number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number')(default 0)  |  地图的初始倾斜度，以距离屏幕平面(0-60)的角度来衡量。如果在构造函数选项中没有指定pitch, Mapbox GL JS会在map的style对象中寻找它。如果样式中没有指定它，它也将默认为0。  |  number  |
|  options.bounds [LngLatBoundsLike](https://www.mapbox.com/mapbox-gl-js/api#lnglatboundslike 'https://www.mapbox.com/mapbox-gl-js/api#lnglatboundslike')?  |  地图的初始边界。如果指定了界限，它将覆盖center和zoom构造函数选项。  |  LngLatBoundsLike  |
|  options.renderWorldCopies [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为真，当缩小时，世界的多个副本将被渲染。  |  boolean  |
|  options.maxTileCacheSizem [number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number')(default null)  |  给定源的tile缓存中存储的tile的最大数量。如果省略，缓存将根据当前视图动态调整大小。  |  number  |
|  options.localIdeographFontFamily [string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String')(default null)  |  如果指定，定义一个CSS font-family，用于在“CJK统一表意文字”和“韩文音节”范围内本地重写字形。在这些范围内，除了字体权重关键字(轻/普通/中/粗体)外，地图样式的字体设置将被忽略。此选项的目的是避免频繁使用带宽的符号服务器请求。(参阅[使用本地产生的表意文字](https://www.mapbox.com/mapbox-gl-js/example/local-ideographs 'https://www.mapbox.com/mapbox-gl-js/example/local-ideographs'))  |  string  |
|  options.transformRequest RequestTransformFunction(default null)  |  映射发出外部URL请求之前的回调运行。回调可用于修改url、设置标题或设置跨源请求的凭证属性。希望返回一个具有url属性和可选头和凭证属性的对象。  |  null  |
|  options.collectResourceTiming [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default false)  |  如果正确，将为GeoJSON和Vector Tile web工作人员发出的请求收集资源定时API信息(此信息通常无法从主Javascript线程访问)。相关数据事件的resourceTiming属性将返回信息。  |  boolean  |
|  options.fadeDuration [number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number')(default 300)  |  为标签冲突控制淡入/淡出动画的持续时间，以毫秒为单位。此设置影响所有符号层。此设置不会影响运行时样式转换或光栅瓷砖交叉褪色的持续时间。  |  number  |
|  options.crossSourceCollisions [boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean 'https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean')(default true)  |  如果为真，则来自多个源的符号可以在碰撞检测过程中相互碰撞。如果为false，则对每个源中的符号分别执行碰撞检测。  |  boolean  |




