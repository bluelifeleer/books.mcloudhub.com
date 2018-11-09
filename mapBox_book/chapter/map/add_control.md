### map.addControl

##### map.addControl用于向地图中添加控件

```
addControl(control, position?)
```

##### 常用控件

* 导航控件(NavigationControl)
* * 导航控制控制包括缩放按钮和指南针。

```
new NavigationControl(options: Object?)
```
* * 参数
* * * options(Object?)

|  名称  |  描述  |  值类型  |
|----|----|----|
|  options.showCompassBoolean(default true)  |  是否显示指南针按纽，如果是true则显示，默认为true  |  Boolen  |
|  options.showZoomBoolean(default true)  |  是否显示放大缩小按纽，如果是true则显示，默认为true  |  Boolen  |

* * 实例
```
var nav = new mapboxgl.NavigationControl();
map.addControl(nav, 'top-left');
```

* 获取当前位置控件(GeolocateControl)
* * GeolocateControl控件提供一个按钮，该按钮使用浏览器的地理定位API在地图上定位用户。
* * 并非所有浏览器都支持地理定位，一些用户可能会禁用该功能。包括Chrome在内的现代浏览器的地理定位支持需要通过HTTPS提供站点服务。如果地理位置支持不可用，那么地理位置控制将不可见。
* * 应用的缩放级别取决于设备提供的地理定位的准确性。
* * 地球控制有两种模式。如果trackUserLocation为false(默认值)，控件就充当一个按钮，当按下按钮时，该按钮将设置地图的摄像头以目标用户位置。如果用户移动，地图将不会更新。这是最适合桌面的。如果trackUserLocation为真，则控件将充当一个切换按钮，当激活时，用户的位置将被主动监视以进行更改。在这种模式下，地球控制有三种状态:
* * 激活-地图的相机自动更新，当用户的位置改变，保持位置点在中心。
* * 被动-用户的位置点会自动更新，但地图的摄像头不会。
* * 禁用

```
new GeolocateControl(options: Object?)
```

* * 参数
* * * options(Object?)

|  名称  |  描述  |  值类型  |
|----|----|----|
|  options.positionOptionsObject(default {enableHighAccuracy:false,timeout:6000})  |  地理定位API PositionOptions对象。  |    |
|  options.fitBoundsOptionsObject(default {maxZoom:15})  |  一个fitBounds options对象，当地图被平移和缩放到用户的位置时使用。默认情况下，使用maxZoom 15来限制地图缩放到非常精确的位置。  |    |
|  options.trackUserLocationObject(default false)  |  如果为真，Geolocate控件将成为一个切换按钮，当激活时，地图将接收到更新到用户的位置，因为它的变化。  |    |
|  options.showUserLocationObject(default true)  |  默认情况下，用户所在位置的地图上会显示一个点。设置为false以禁用。默认为true  |    |

* * 实例
```
map.addControl(new mapboxgl.GeolocateControl({
    positionOptions: {
        enableHighAccuracy: true
    },
    trackUserLocation: true
}));
```

* 属性控制控件(AttributionControl)显示地图的属性信息。
```
new AttributionControl(options: Object?)
```

* * 参数
* * * options(Object?)(default {})

|  名称  |  描述  |  值类型  |
|----|----|----|
|  options.compactboolean?  |  如果true force显示鼠标悬停时的完整归因，或者false force完全归因控制。默认属性是一个响应性属性，当地图宽度小于640像素时就会崩溃。  |    |
|  options.customAttribution(string | Array<string>)?  |  除了任何其他属性之外显示的字符串或字符串。  |    |

* * 实例
```
var map = new mapboxgl.Map({attributionControl: false})
    .addControl(new mapboxgl.AttributionControl({
        compact: true
    }));
```


* 距离比例尺控件(ScaleControl)

```
new ScaleControl(options: Object?)
```

* * 参数
* * * options(Object?)

|  名称  |  描述  |  值类型  |
|----|----|----|
|  options.maxWidthnumber(default  '100')  |  缩放控件的最大长度(以像素为单位)。  |    |
|  options.unitstring(default 'metric')  |    |    |


* * 实例

```
var scale = new mapboxgl.ScaleControl({
    maxWidth: 80,
    unit: 'imperial'
});
map.addControl(scale);

scale.setUnit('metric');
```

	
