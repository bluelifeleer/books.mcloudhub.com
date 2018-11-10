### LngLatBounds

#### LngLatBounds对象表示一个地理边界框，由其在经纬度上的西南和东北点定义。

#### 如果没有向构造函数提供参数，则创建一个空边界框。

#### 注意，任何接受LngLatBounds对象作为参数或选项的Mapbox GL方法也可以接受两个LngLatBounds样构造的数组，并将执行隐式转换。这种灵活的类型被记录为LngLatBoundsLike。

### 实例

```
new LngLatBounds(sw: LngLatLike?, ne: LngLatLike?)
```

### 参数

|  名称  |  描述  |  值  |
|----|----|----|
|  sw(LngLatLike?)  |  包围盒的西南角。  |  LngLatLike  |
|  ne(LngLatLike?)  |  包围盒的东北角。  |  LngLatLike  |


### 方法

|  名称  |  描述  |  值  |
|----|----|----|
|  convert(input)  |  将数组转换为LngLatBounds对象。如果传入一个LngLatBounds对象，函数将返回它不变。在内部，函数调用LngLat#convert将数组转换为LngLat值。  |  输入(LngLatBoundsLike)要转换的两个坐标数组，或返回的LngLatBounds对象。  |
|  setNorthEast(ne)  |  设置边界框的东北角  |  ne(LngLatLike)  |
|  setSouthWest(sw)  |  置边框的西南角  |  sw(LngLatLike)  |
|  extend(obj)  |  扩展边界以包含给定的LngLat或LngLatBounds。  |  obj((LngLat | LngLatBounds))object to extend to  |
|  getCenter()  |  返回与边框角等距的地理坐标。  |    |
|  getSouthWest()  |  返回绑定框的西南角。  |    |
|  getNorthEast()  |  返回包围框的东北角。 |    |
|  getNorthWest()  |  返回绑定框的西北角。  |    |
|  getSouthEast()  |  返回包围盒的东南角。  |    |
|  getWest()  |  返回包围盒的西侧边缘。  |    |
|  getSouth()  |  返回包围盒的南边缘。  |    |
|  getEast()  |  返回包围盒的东部边缘。  |    |
|  getNorth()  |  返回包围盒的北边缘。  |    |
|  toArray()  |  返回作为数组表示的边框。  |    |
|  toString()  |  返回作为字符串表示的边框。  |    |
|  isEmpty()  |  检查边界框是否为空/空类型框。  |    |

### 实例

```
var sw = new mapboxgl.LngLat(-73.9876, 40.7661);
var ne = new mapboxgl.LngLat(-73.9397, 40.8002);
var llb = new mapboxgl.LngLatBounds(sw, ne);
```

### 英语学习fnaq

#### bound
##### 英 [baʊnd]  美 [baʊnd] 
###### adj. 有义务的；受约束的；装有封面的
###### vt. 束缚；使跳跃
###### n. 范围；跳跃
###### vi. 限制；弹起

#### bounds
##### 英  美 [baʊndz] 
###### n. 界限；跳动（bound的复数）
###### v. 跳跃；弹回；限定；邻接（bound的三单形式）
###### n. (Bounds)人名；(英)邦兹