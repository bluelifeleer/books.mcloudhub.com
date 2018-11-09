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
