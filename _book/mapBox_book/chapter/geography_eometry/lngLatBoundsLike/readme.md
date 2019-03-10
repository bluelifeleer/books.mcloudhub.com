### LngLatBoundsLike

#### 一个LngLatBounds对象，一个类似LngLatBounds对象的数组，按[西南，东北]顺序，或一个数字数组在[西，南，东，北]顺序。

### 实例

```
var v1 = new mapboxgl.LngLatBounds(
  new mapboxgl.LngLat(-73.9876, 40.7661),
  new mapboxgl.LngLat(-73.9397, 40.8002)
);
var v2 = new mapboxgl.LngLatBounds([-73.9876, 40.7661], [-73.9397, 40.8002])
var v3 = [[-73.9876, 40.7661], [-73.9397, 40.8002]];
```