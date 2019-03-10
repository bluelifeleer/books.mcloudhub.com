### LngLat(经纬度)

#### LngLat对象表示给定的经纬度坐标，以度数表示。
#### Mapbox GL使用经度、纬度坐标顺序(与纬度、经度相反)来匹配GeoJSON。
#### 注意，任何接受LngLat对象作为参数或选项的Mapbox GL方法也可以接受一个包含两个数字的数组，并执行隐式转换。这种灵活的类型被记录为LngLatLike。

### 语法

```
new LngLat(lng: number, lat: number)
```

### 参数

|  名称  |  描述  |  值  |
|----|----|----|
|  lng(number)  |  经度，用度数表示  |    |
|  lat(number)  |  纬度，用度数表示  |    |

lng(number)Longitude, measured in degrees.
lat(number)Latitude, measured in degrees.

### 方法

|  名称  |  描述  |  值  |
|----|----|----|
|  convert(input)  |  将一个包含两个数字的数组或具有lng和lat或lon和lat属性的对象转换为LngLat对象。如果传入了一个LngLat对象，函数将原封不动地返回它。  |  input(LngLatLike)要转换的两个数字或对象的数组，或要返回的LngLat对象。  |
|  wrap()  |  返回一个新的LngLat对象，其经度被包装到范围(-180,180)。  |    |
|  toArray()  |  返回以两个数字数组表示的坐标。  |    |
|  toString()  |  返回作为字符串表示的坐标。  |    |
|  toBounds(radius)  |  从被给定半径扩展的坐标返回LngLatBounds。  |    |

### 实例

```
var ll = new mapboxgl.LngLat(-73.9749, 40.7736);
```



### 英语学习专区

#### measured
##### 英 ['meʒəd]  美 ['mɛʒɚd] 
###### adj. 量过的；慎重的；基于标准的；有规则的
###### v. 测量，判断（measure的过去分词）

#### degrees
##### 英  美 
###### n. 角度，学历；度数（degree的复数）

#### wrap
##### 英 [ræp]  美 [ræp] 
###### vt. 包；缠绕；隐藏；掩护
###### vi. 包起来；缠绕；穿外衣
###### n. 外套；围巾